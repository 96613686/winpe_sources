# SPPGetTamperErrorCode(long *,int *)

- ea: `0x180023018`
- end: `0x18002312d`
- name: `?SPPGetTamperErrorCode@@YAJPEAJPEAH@Z`
- size: `277`
- prototype: `__int64 __fastcall(int *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180023134`

## callees

- `0x180003520`
- `0x180004288`
- `0x180023018`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800230f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800230f4`
- `SLC!SLGetServiceInformation` at `0x180023086`
- `SLC!SLGetServiceInformation` at `0x180023086`
- `SLC!SLOpen` at `0x18002304f`
- `SLC!SLOpen` at `0x18002304f`
- `SLC!SLClose` at `0x180023111`
- `SLC!SLClose` at `0x180023111`

## pseudocode

```c
__int64 __fastcall SPPGetTamperErrorCode(int *a1, int *a2)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  PBYTE v7; // rax
  PBYTE ppbValue; // [rsp+30h] [rbp-10h] BYREF
  HSLC phSLC; // [rsp+38h] [rbp-8h] BYREF
  UINT pcbValue; // [rsp+70h] [rbp+30h] BYREF
  SLDATATYPE peDataType; // [rsp+78h] [rbp+38h] BYREF

  phSLC = 0;
  peDataType = SL_DATA_NONE;
  pcbValue = 0;
  ppbValue = 0;
  v4 = SLOpen(&phSLC);
  v5 = v4;
  if ( v4 < 0
    || (v4 = SLGetServiceInformation(phSLC, L"SystemState", &peDataType, &pcbValue, &ppbValue), v5 = v4, v4 < 0) )
  {
    v6 = (unsigned int)v4;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_14;
  }
  if ( pcbValue != 4 )
  {
    v5 = -2147418113;
    v6 = 2147549183LL;
    goto LABEL_3;
  }
  v7 = ppbValue;
  *a2 = 1;
  if ( (*v7 & 0x20) != 0 )
  {
    *a1 = -1073425151;
  }
  else if ( (*v7 & 8) != 0 )
  {
    *a1 = -1073425663;
  }
  else if ( (*v7 & 2) != 0 )
  {
    *a1 = -1073426173;
  }
  else
  {
    *a1 = 0;
    *a2 = 0;
  }
LABEL_14:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( ppbValue )
  {
    LocalFree(ppbValue);
    ppbValue = 0;
  }
  if ( phSLC )
    SLClose(phSLC);
  return v5;
}

```

## disassembly

```asm
0x180023018  mov     [rsp-18h+arg_0], rbx
0x18002301d  push    rbp
0x18002301e  push    rsi
0x18002301f  push    rdi
0x180023020  mov     rbp, rsp
0x180023023  sub     rsp, 40h
0x180023027  mov     rdi, rcx
0x18002302a  mov     [rbp+phSLC], 0
0x180023032  lea     rcx, [rbp+phSLC]; phSLC
0x180023036  mov     [rbp+peDataType], 0
0x18002303d  mov     rsi, rdx
0x180023040  mov     [rbp+pcbValue], 0
0x180023047  mov     [rbp+var_10], 0
0x18002304f  call    cs:__imp_SLOpen
0x180023056  nop     dword ptr [rax+rax+00h]
0x18002305b  mov     ebx, eax
0x18002305d  test    eax, eax
0x18002305f  jns     short loc_18002306A
0x180023061  mov     ecx, eax
0x180023063  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180023068  jmp     short loc_1800230E4
0x18002306a  mov     rcx, [rbp+phSLC]; hSLC
0x18002306e  lea     rax, [rbp+var_10]
0x180023072  lea     r9, [rbp+pcbValue]; pcbValue
0x180023076  mov     [rsp+40h+ppbValue], rax; ppbValue
0x18002307b  lea     r8, [rbp+peDataType]; peDataType
0x18002307f  lea     rdx, aSystemstate; "SystemState"
0x180023086  call    cs:__imp_SLGetServiceInformation
0x18002308d  nop     dword ptr [rax+rax+00h]
0x180023092  mov     ebx, eax
0x180023094  test    eax, eax
0x180023096  js      short loc_180023061
0x180023098  cmp     [rbp+pcbValue], 4
0x18002309c  jz      short loc_1800230A7
0x18002309e  mov     ebx, 8000FFFFh
0x1800230a3  mov     ecx, ebx
0x1800230a5  jmp     short loc_180023063
0x1800230a7  mov     rax, [rbp+var_10]
0x1800230ab  mov     dword ptr [rsi], 1
0x1800230b1  test    byte ptr [rax], 20h
0x1800230b4  jz      short loc_1800230BE
0x1800230b6  mov     dword ptr [rdi], 0C004D501h
0x1800230bc  jmp     short loc_1800230E4
0x1800230be  test    byte ptr [rax], 8
0x1800230c1  jz      short loc_1800230CB
0x1800230c3  mov     dword ptr [rdi], 0C004D301h
0x1800230c9  jmp     short loc_1800230E4
0x1800230cb  test    byte ptr [rax], 2
0x1800230ce  jz      short loc_1800230D8
0x1800230d0  mov     dword ptr [rdi], 0C004D103h
0x1800230d6  jmp     short loc_1800230E4
0x1800230d8  mov     dword ptr [rdi], 0
0x1800230de  mov     dword ptr [rsi], 0
0x1800230e4  mov     ecx, ebx
0x1800230e6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800230eb  mov     rcx, [rbp+var_10]; hMem
0x1800230ef  test    rcx, rcx
0x1800230f2  jz      short loc_180023108
0x1800230f4  call    cs:__imp_LocalFree
0x1800230fb  nop     dword ptr [rax+rax+00h]
0x180023100  mov     [rbp+var_10], 0
0x180023108  mov     rcx, [rbp+phSLC]; hSLC
0x18002310c  test    rcx, rcx
0x18002310f  jz      short loc_18002311D
0x180023111  call    cs:__imp_SLClose
0x180023118  nop     dword ptr [rax+rax+00h]
0x18002311d  mov     eax, ebx
0x18002311f  mov     rbx, [rsp+40h+arg_0]
0x180023124  add     rsp, 40h
0x180023128  pop     rdi
0x180023129  pop     rsi
0x18002312a  pop     rbp
0x18002312b  retn
```
