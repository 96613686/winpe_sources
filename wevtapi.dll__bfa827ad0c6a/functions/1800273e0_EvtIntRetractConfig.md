# EvtIntRetractConfig

- ea: `0x1800273e0`
- end: `0x18002755c`
- name: `EvtIntRetractConfig`
- size: `380`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180007940`
- `0x180007aa0`
- `0x180023548`
- `0x1800273e0`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002753d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002753d`
- `RPCRT4!NdrClientCall3` at `0x1800274a3`
- `RPCRT4!NdrClientCall3` at `0x1800274a3`

## pseudocode

```c
__int64 __fastcall EvtIntRetractConfig(__int64 a1, __int64 a2, int a3)
{
  unsigned int Pointer; // ebx
  unsigned int v6; // edi
  DWORD v7; // ebx
  int v9; // [rsp+28h] [rbp-70h]
  EvtException *v10; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v11[3]; // [rsp+38h] [rbp-60h] BYREF
  unsigned int v12; // [rsp+50h] [rbp-48h]
  __int64 v13; // [rsp+54h] [rbp-44h]
  char v14; // [rsp+5Ch] [rbp-3Ch]
  __int128 pExceptionObject; // [rsp+60h] [rbp-38h] BYREF
  __int64 v16; // [rsp+70h] [rbp-28h]
  int v17; // [rsp+78h] [rbp-20h]
  int v18; // [rsp+7Ch] [rbp-1Ch]
  int v19; // [rsp+80h] [rbp-18h]
  __int64 v20; // [rsp+B8h] [rbp+20h] BYREF

  try
  {
    if ( (a3 & 0xFFFFFFFE) != 0 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
      }
      pExceptionObject = 0;
      v16 = 0;
      v17 = 87;
      v18 = -1;
      v19 = 417;
      throw (EvtException *)&pExceptionObject;
    }
    GetSession(&v20);
    v9 = a3;
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0x10u,
                              0,
                              *(_QWORD *)(v20 + 72),
                              a2,
                              v9).Pointer;
    v6 = 0;
    if ( Pointer )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, Pointer);
      }
      v11[0] = &word_18004024A;
      v11[1] = 0;
      v11[2] = 0;
      v12 = Pointer;
      v13 = -1;
      v14 = 0;
      throw (EvtException *)v11;
    }
    v7 = 0;
    wmi::AutoRef<Object>::Release(&v20);
  }
  catch ( EvtException *v10 )
  {
    v6 = 0;
    v7 = *((_DWORD *)v10 + 6);
  }
  if ( (a3 & 0xFFFFFFFE) != 0 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
    }
    pExceptionObject = 0;
    v16 = 0;
    v17 = 87;
    v18 = -1;
    v19 = 417;
    throw (EvtException *)&pExceptionObject;
  }
  GetSession(&v20);
  v9 = a3;
}

```

## disassembly

```asm
0x1800273e0  mov     [rsp+arg_0], rbx
0x1800273e5  push    rdi
0x1800273e6  sub     rsp, 90h
0x1800273ed  mov     ebx, r8d
0x1800273f0  mov     rdi, rdx
0x1800273f3  test    ebx, 0FFFFFFFEh
0x1800273f9  jz      short loc_18002746F
0x1800273fb  lea     rax, WPP_GLOBAL_Control
0x180027402  mov     rcx, cs:WPP_GLOBAL_Control
0x180027409  cmp     rcx, rax
0x18002740c  jz      short loc_180027433
0x18002740e  test    byte ptr [rcx+1Ch], 1
0x180027412  jz      short loc_180027433
0x180027414  cmp     byte ptr [rcx+19h], 2
0x180027418  jb      short loc_180027433
0x18002741a  mov     edx, 11h
0x18002741f  lea     r9d, [rdx+46h]
0x180027423  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x18002742a  mov     rcx, [rcx+10h]
0x18002742e  call    WPP_SF_D
0x180027433  xorps   xmm0, xmm0
0x180027436  movdqu  [rsp+98h+pExceptionObject], xmm0
0x18002743c  xor     edi, edi
0x18002743e  mov     [rsp+98h+var_28], rdi
0x180027443  mov     [rsp+98h+var_20], 57h ; 'W'
0x18002744b  mov     [rsp+98h+var_1C], 0FFFFFFFFh
0x180027453  mov     [rsp+98h+var_18], 1A1h
0x18002745e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180027465  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18002746a  call    _CxxThrowException_0
0x18002746f  mov     rdx, rcx
0x180027472  lea     rcx, [rsp+98h+arg_18]; void *
0x18002747a  call    ?GetSession@@YA?AV?$AutoRef@VSession@@@wmi@@PEAX@Z; GetSession(void *)
0x18002747f  nop
0x180027480  mov     [rsp+98h+var_70], ebx
0x180027484  mov     [rsp+98h+var_78], rdi
0x180027489  mov     r9, [rsp+98h+arg_18]
0x180027491  mov     r9, [r9+48h]
0x180027495  xor     r8d, r8d; pReturnValue
0x180027498  lea     edx, [r8+10h]; nProcNum
0x18002749c  lea     rcx, pProxyInfo; pProxyInfo
0x1800274a3  call    cs:__imp_NdrClientCall3
0x1800274a9  mov     rbx, rax
0x1800274ac  xor     edi, edi
0x1800274ae  test    ebx, ebx
0x1800274b0  jz      short loc_180027520
0x1800274b2  lea     rax, WPP_GLOBAL_Control
0x1800274b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800274c0  cmp     rcx, rax
0x1800274c3  jz      short loc_1800274E7
0x1800274c5  test    byte ptr [rcx+1Ch], 1
0x1800274c9  jz      short loc_1800274E7
0x1800274cb  cmp     byte ptr [rcx+19h], 2
0x1800274cf  jb      short loc_1800274E7
0x1800274d1  lea     edx, [rdi+12h]
0x1800274d4  mov     r9d, ebx
0x1800274d7  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x1800274de  mov     rcx, [rcx+10h]
0x1800274e2  call    WPP_SF_D
0x1800274e7  lea     rax, word_18004024A
0x1800274ee  mov     [rsp+98h+var_60], rax
0x1800274f3  mov     [rsp+98h+var_58], rdi
0x1800274f8  mov     [rsp+98h+var_50], rdi
0x1800274fd  mov     [rsp+98h+var_48], ebx
0x180027501  mov     [rsp+98h+var_44], 0FFFFFFFFFFFFFFFFh
0x18002750a  mov     [rsp+98h+var_3C], dil
0x18002750f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180027516  lea     rcx, [rsp+98h+var_60]; pExceptionObject
0x18002751b  call    _CxxThrowException_0
0x180027520  mov     ebx, edi
0x180027522  lea     rcx, [rsp+98h+arg_18]; void *
0x18002752a  call    ?Release@?$AutoRef@VObject@@@wmi@@QEAAXXZ; wmi::AutoRef<Object>::Release(void)
0x18002752f  nop
0x180027530  jmp     short loc_18002753B
0x180027532  xor     edi, edi
0x180027534  mov     ebx, [rsp+98h+arg_10]
0x18002753b  mov     ecx, ebx; dwErrCode
0x18002753d  call    cs:__imp_SetLastError
0x180027543  test    ebx, ebx
0x180027545  setz    dil
0x180027549  mov     eax, edi
0x18002754b  mov     rbx, [rsp+98h+arg_0]
0x180027553  add     rsp, 90h
0x18002755a  pop     rdi
0x18002755b  retn
```
