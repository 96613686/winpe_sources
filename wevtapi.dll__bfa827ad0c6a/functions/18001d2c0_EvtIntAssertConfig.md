# EvtIntAssertConfig

- ea: `0x18001d2c0`
- end: `0x18001d44a`
- name: `EvtIntAssertConfig`
- size: `394`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180006870`
- `0x180007940`
- `0x18001d2c0`
- `0x180023548`
- `0x180038fa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d337`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d337`
- `RPCRT4!NdrClientCall3` at `0x18001d30d`
- `RPCRT4!NdrClientCall3` at `0x18001d30d`

## pseudocode

```c
__int64 __fastcall EvtIntAssertConfig(__int64 a1, __int64 a2, int a3)
{
  unsigned int Pointer; // ebx
  unsigned int v6; // edi
  DWORD v7; // ebx
  EvtException *v9; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v10[3]; // [rsp+38h] [rbp-60h] BYREF
  unsigned int v11; // [rsp+50h] [rbp-48h]
  __int64 v12; // [rsp+54h] [rbp-44h]
  char v13; // [rsp+5Ch] [rbp-3Ch]
  __int128 pExceptionObject; // [rsp+60h] [rbp-38h] BYREF
  __int64 v15; // [rsp+70h] [rbp-28h]
  int v16; // [rsp+78h] [rbp-20h]
  int v17; // [rsp+7Ch] [rbp-1Ch]
  int v18; // [rsp+80h] [rbp-18h]
  wmi::RefBase *v19; // [rsp+B8h] [rbp+20h] BYREF

  try
  {
    if ( (a3 & 0xFFFFFFFE) != 0 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
      }
      pExceptionObject = 0;
      v15 = 0;
      v16 = 87;
      v17 = -1;
      v18 = 380;
      throw (EvtException *)&pExceptionObject;
    }
    GetSession(&v19);
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0xFu,
                              0,
                              *((_QWORD *)v19 + 9),
                              a2,
                              a3).Pointer;
    v6 = 0;
    if ( Pointer )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, Pointer);
      }
      v10[0] = &word_18004024A;
      v10[1] = 0;
      v10[2] = 0;
      v11 = Pointer;
      v12 = -1;
      v13 = 0;
      throw (EvtException *)v10;
    }
    v7 = 0;
    if ( v19 )
      wmi::RefBase::Release(v19);
  }
  catch ( EvtException *v9 )
  {
    v6 = 0;
    v7 = *((_DWORD *)v9 + 6);
  }
  if ( (a3 & 0xFFFFFFFE) != 0 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids, 87);
    }
    pExceptionObject = 0;
    v15 = 0;
    v16 = 87;
    v17 = -1;
    v18 = 380;
    throw (EvtException *)&pExceptionObject;
  }
  GetSession(&v19);
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xFu, 0, *((_QWORD *)v19 + 9), a2, a3).Pointer;
}

```

## disassembly

```asm
0x18001d2c0  mov     rax, rsp
0x18001d2c3  mov     [rax+8], rbx
0x18001d2c7  push    rdi
0x18001d2c8  sub     rsp, 90h
0x18001d2cf  mov     ebx, r8d
0x18001d2d2  mov     rdi, rdx
0x18001d2d5  test    ebx, 0FFFFFFFEh
0x18001d2db  jnz     short loc_18001D356
0x18001d2dd  mov     rdx, rcx
0x18001d2e0  lea     rcx, [rax+20h]; void *
0x18001d2e4  call    ?GetSession@@YA?AV?$AutoRef@VSession@@@wmi@@PEAX@Z; GetSession(void *)
0x18001d2e9  nop
0x18001d2ea  mov     [rsp+98h+var_70], ebx
0x18001d2ee  mov     [rsp+98h+var_78], rdi
0x18001d2f3  mov     r9, [rsp+98h+arg_18]
0x18001d2fb  mov     r9, [r9+48h]
0x18001d2ff  xor     r8d, r8d; pReturnValue
0x18001d302  lea     edx, [r8+0Fh]; nProcNum
0x18001d306  lea     rcx, pProxyInfo; pProxyInfo
0x18001d30d  call    cs:__imp_NdrClientCall3
0x18001d313  mov     rbx, rax
0x18001d316  xor     edi, edi
0x18001d318  test    ebx, ebx
0x18001d31a  jnz     loc_18001D3CB
0x18001d320  mov     ebx, edi
0x18001d322  mov     rcx, [rsp+98h+arg_18]; this
0x18001d32a  test    rcx, rcx
0x18001d32d  jz      short loc_18001D335
0x18001d32f  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18001d334  nop
0x18001d335  mov     ecx, ebx; dwErrCode
0x18001d337  call    cs:__imp_SetLastError
0x18001d33d  test    ebx, ebx
0x18001d33f  setz    dil
0x18001d343  mov     eax, edi
0x18001d345  mov     rbx, [rsp+98h+arg_0]
0x18001d34d  add     rsp, 90h
0x18001d354  pop     rdi
0x18001d355  retn
0x18001d356  lea     rax, WPP_GLOBAL_Control
0x18001d35d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d364  cmp     rcx, rax
0x18001d367  jz      short loc_18001D38E
0x18001d369  test    byte ptr [rcx+1Ch], 1
0x18001d36d  jz      short loc_18001D38E
0x18001d36f  cmp     byte ptr [rcx+19h], 2
0x18001d373  jb      short loc_18001D38E
0x18001d375  mov     edx, 0Fh
0x18001d37a  lea     r9d, [rdx+48h]
0x18001d37e  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x18001d385  mov     rcx, [rcx+10h]
0x18001d389  call    WPP_SF_D
0x18001d38e  xorps   xmm0, xmm0
0x18001d391  movdqu  [rsp+98h+pExceptionObject], xmm0
0x18001d397  xor     edi, edi
0x18001d399  mov     [rsp+98h+var_28], rdi
0x18001d39e  mov     [rsp+98h+var_20], 57h ; 'W'
0x18001d3a6  mov     [rsp+98h+var_1C], 0FFFFFFFFh
0x18001d3ae  mov     [rsp+98h+var_18], 17Ch
0x18001d3b9  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001d3c0  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18001d3c5  call    _CxxThrowException_0
0x18001d3cb  lea     rax, WPP_GLOBAL_Control
0x18001d3d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3d9  cmp     rcx, rax
0x18001d3dc  jz      short loc_18001D402
0x18001d3de  test    byte ptr [rcx+1Ch], 1
0x18001d3e2  jz      short loc_18001D402
0x18001d3e4  cmp     byte ptr [rcx+19h], 2
0x18001d3e8  jb      short loc_18001D402
0x18001d3ea  mov     edx, 10h
0x18001d3ef  mov     r9d, ebx
0x18001d3f2  lea     r8, WPP_50a4b5d3db573bd708b949f391e8ee2a_Traceguids
0x18001d3f9  mov     rcx, [rcx+10h]
0x18001d3fd  call    WPP_SF_D
0x18001d402  lea     rax, word_18004024A
0x18001d409  mov     [rsp+98h+var_60], rax
0x18001d40e  mov     [rsp+98h+var_58], rdi
0x18001d413  mov     [rsp+98h+var_50], rdi
0x18001d418  mov     [rsp+98h+var_48], ebx
0x18001d41c  mov     [rsp+98h+var_44], 0FFFFFFFFFFFFFFFFh
0x18001d425  mov     [rsp+98h+var_3C], dil
0x18001d42a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001d431  lea     rcx, [rsp+98h+var_60]; pExceptionObject
0x18001d436  call    _CxxThrowException_0
0x18001d43c  xor     edi, edi
0x18001d43e  mov     ebx, [rsp+98h+arg_10]
0x18001d445  jmp     loc_18001D335
```
