# CLicensingStateTools::get_SystemStateFlags(tagSYSTEM_STATE_FLAGS *)

- ea: `0x180019850`
- end: `0x180019930`
- name: `?get_SystemStateFlags@CLicensingStateTools@@UEAAJPEAW4tagSYSTEM_STATE_FLAGS@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(CLicensingStateTools *__hidden this, enum tagSYSTEM_STATE_FLAGS *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180003520`
- `0x180004288`
- `0x180019850`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800198fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800198fc`
- `SLC!SLGetServiceInformation` at `0x1800198c5`
- `SLC!SLGetServiceInformation` at `0x1800198c5`
- `SLC!SLOpen` at `0x180019893`
- `SLC!SLOpen` at `0x180019893`
- `SLC!SLClose` at `0x180019919`
- `SLC!SLClose` at `0x180019919`

## pseudocode

```c
__int64 __fastcall CLicensingStateTools::get_SystemStateFlags(
        CLicensingStateTools *this,
        enum tagSYSTEM_STATE_FLAGS *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  HRESULT v5; // eax
  HSLC phSLC; // [rsp+30h] [rbp-10h] BYREF
  UINT pcbValue; // [rsp+68h] [rbp+28h] BYREF
  SLDATATYPE peDataType; // [rsp+70h] [rbp+30h] BYREF
  PBYTE ppbValue; // [rsp+78h] [rbp+38h] BYREF

  phSLC = 0;
  peDataType = SL_DATA_NONE;
  pcbValue = 0;
  ppbValue = 0;
  if ( !a2 )
  {
    v3 = -2147024809;
LABEL_3:
    v4 = v3;
LABEL_4:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
    goto LABEL_11;
  }
  v5 = SLOpen(&phSLC);
  v3 = v5;
  if ( v5 < 0
    || (v5 = SLGetServiceInformation(phSLC, L"SystemState", &peDataType, &pcbValue, &ppbValue), v3 = v5, v5 < 0) )
  {
    v4 = (unsigned int)v5;
    goto LABEL_4;
  }
  if ( pcbValue != 4 )
  {
    v3 = -2147418113;
    goto LABEL_3;
  }
  *(_DWORD *)a2 = *(_DWORD *)ppbValue;
LABEL_11:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( ppbValue )
  {
    LocalFree(ppbValue);
    ppbValue = 0;
  }
  if ( phSLC )
    SLClose(phSLC);
  return v3;
}

```

## disassembly

```asm
0x180019850  push    rbp
0x180019852  push    rbx
0x180019853  push    rdi
0x180019854  mov     rbp, rsp
0x180019857  sub     rsp, 40h
0x18001985b  mov     [rbp+phSLC], 0
0x180019863  mov     rdi, rdx
0x180019866  mov     [rbp+peDataType], 0
0x18001986d  mov     [rbp+pcbValue], 0
0x180019874  mov     [rbp+arg_18], 0
0x18001987c  test    rdx, rdx
0x18001987f  jnz     short loc_18001988F
0x180019881  mov     ebx, 80070057h
0x180019886  mov     ecx, ebx
0x180019888  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001988d  jmp     short loc_1800198EC
0x18001988f  lea     rcx, [rbp+phSLC]; phSLC
0x180019893  call    cs:__imp_SLOpen
0x18001989a  nop     dword ptr [rax+rax+00h]
0x18001989f  mov     ebx, eax
0x1800198a1  test    eax, eax
0x1800198a3  jns     short loc_1800198A9
0x1800198a5  mov     ecx, eax
0x1800198a7  jmp     short loc_180019888
0x1800198a9  mov     rcx, [rbp+phSLC]; hSLC
0x1800198ad  lea     rax, [rbp+arg_18]
0x1800198b1  lea     r9, [rbp+pcbValue]; pcbValue
0x1800198b5  mov     [rsp+40h+ppbValue], rax; ppbValue
0x1800198ba  lea     r8, [rbp+peDataType]; peDataType
0x1800198be  lea     rdx, aSystemstate; "SystemState"
0x1800198c5  call    cs:__imp_SLGetServiceInformation
0x1800198cc  nop     dword ptr [rax+rax+00h]
0x1800198d1  mov     ebx, eax
0x1800198d3  test    eax, eax
0x1800198d5  js      short loc_1800198A5
0x1800198d7  cmp     [rbp+pcbValue], 4
0x1800198db  jz      short loc_1800198E4
0x1800198dd  mov     ebx, 8000FFFFh
0x1800198e2  jmp     short loc_180019886
0x1800198e4  mov     rax, [rbp+arg_18]
0x1800198e8  mov     ecx, [rax]
0x1800198ea  mov     [rdi], ecx
0x1800198ec  mov     ecx, ebx
0x1800198ee  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800198f3  mov     rcx, [rbp+arg_18]; hMem
0x1800198f7  test    rcx, rcx
0x1800198fa  jz      short loc_180019910
0x1800198fc  call    cs:__imp_LocalFree
0x180019903  nop     dword ptr [rax+rax+00h]
0x180019908  mov     [rbp+arg_18], 0
0x180019910  mov     rcx, [rbp+phSLC]; hSLC
0x180019914  test    rcx, rcx
0x180019917  jz      short loc_180019925
0x180019919  call    cs:__imp_SLClose
0x180019920  nop     dword ptr [rax+rax+00h]
0x180019925  mov     eax, ebx
0x180019927  add     rsp, 40h
0x18001992b  pop     rdi
0x18001992c  pop     rbx
0x18001992d  pop     rbp
0x18001992e  retn
```
