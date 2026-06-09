# WinStationShadow

- ea: `0x1800219c0`
- end: `0x180021b0d`
- name: `WinStationShadow`
- size: `333`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, __int16)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x180004554`
- `0x180005c30`
- `0x180005fcc`
- `0x180007890`
- `0x180008290`
- `0x180008e30`
- `0x1800219c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021a34`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021a34`
- `RPCRT4!NdrClientCall3` at `0x180021a88`
- `RPCRT4!NdrClientCall3` at `0x180021a88`

## string_xrefs

- `0x1800219fb`: `Failed to open binding`

## pseudocode

```c
char __fastcall WinStationShadow(void *a1, __int64 a2, ULONG SessionId, unsigned __int8 a4, unsigned __int16 a5)
{
  int v5; // r14d
  char v9; // di
  DWORD v10; // ecx
  void *v11; // rax
  int Pointer; // ebx
  unsigned __int16 v14[28]; // [rsp+50h] [rbp-38h] BYREF

  v5 = a4;
  v9 = 0;
  CSmartPublicBinding::CSmartPublicBinding((CSmartPublicBinding *)v14, a1, 1);
  if ( CSmartPublicBinding::operator void *(v14) )
  {
    if ( SessionId == -1 )
    {
      if ( !(unsigned int)IsLocalServer(a1) )
      {
        _DbgPrintMessage(4, "LOGONID_CURRENT specified for a remote server!");
        v10 = 87;
LABEL_6:
        SetLastError(v10);
        goto LABEL_11;
      }
      SessionId = NtCurrentPeb()->SessionId;
    }
    v11 = CSmartPublicBinding::operator void *(v14);
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&stru_1800320E0,
                              5u,
                              0,
                              v11,
                              a2,
                              SessionId,
                              v5,
                              a5).Pointer;
    if ( Pointer >= 0 )
    {
      v9 = 1;
      goto LABEL_11;
    }
    _DbgPrintMessage(8, "RpcShadow failed: 0x%x in %s", Pointer, "WinStationShadow");
    v10 = ConvertHRESULT2WIN32(Pointer);
    goto LABEL_6;
  }
  _DbgPrintMessage(8, "Failed to open binding");
LABEL_11:
  CSmartPublicBinding::~CSmartPublicBinding((CSmartPublicBinding *)v14);
  return v9;
}

```

## disassembly

```asm
0x1800219c0  push    rbx
0x1800219c2  push    rsi
0x1800219c3  push    rdi
0x1800219c4  push    r14
0x1800219c6  push    r15
0x1800219c8  sub     rsp, 60h
0x1800219cc  movzx   r14d, r9b
0x1800219d0  mov     ebx, r8d
0x1800219d3  mov     r15, rdx
0x1800219d6  mov     rsi, rcx
0x1800219d9  xor     edi, edi
0x1800219db  lea     r8d, [rdi+1]; int
0x1800219df  mov     rdx, rcx; void *
0x1800219e2  lea     rcx, [rsp+88h+var_38]; this
0x1800219e7  call    ??0CSmartPublicBinding@@QEAA@PEAXH@Z; CSmartPublicBinding::CSmartPublicBinding(void *,int)
0x1800219ec  lea     rcx, [rsp+88h+var_38]; unsigned __int16 *
0x1800219f1  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x1800219f6  test    rax, rax
0x1800219f9  jnz     short loc_180021A0F
0x1800219fb  lea     rdx, aFailedToOpenBi_0; "Failed to open binding"
0x180021a02  lea     ecx, [rdi+8]; int
0x180021a05  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021a0a  jmp     loc_180021AF4
0x180021a0f  cmp     ebx, 0FFFFFFFFh
0x180021a12  jnz     short loc_180021A4E
0x180021a14  mov     rcx, rsi; void *
0x180021a17  call    ?IsLocalServer@@YAHPEAX@Z; IsLocalServer(void *)
0x180021a1c  test    eax, eax
0x180021a1e  jnz     short loc_180021A3F
0x180021a20  lea     rdx, aLogonidCurrent; "LOGONID_CURRENT specified for a remote "...
0x180021a27  lea     ecx, [rax+4]; int
0x180021a2a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021a2f  mov     ecx, 57h ; 'W'; dwErrCode
0x180021a34  call    cs:__imp_SetLastError
0x180021a3a  jmp     loc_180021AF4
0x180021a3f  mov     rax, gs:60h
0x180021a48  mov     ebx, [rax+2C0h]
0x180021a4e  lea     rcx, [rsp+88h+var_38]; unsigned __int16 *
0x180021a53  call    ??BCSmartPublicBinding@@QEAAPEAXXZ; CSmartPublicBinding::operator void *(void)
0x180021a58  mov     [rsp+88h+var_40], rdi
0x180021a5d  movzx   ecx, [rsp+88h+arg_20]
0x180021a65  mov     [rsp+88h+var_50], ecx
0x180021a69  mov     [rsp+88h+var_58], r14d
0x180021a6e  mov     [rsp+88h+var_60], ebx
0x180021a72  mov     [rsp+88h+var_68], r15
0x180021a77  mov     r9, rax
0x180021a7a  xor     r8d, r8d; pReturnValue
0x180021a7d  lea     edx, [r8+5]; nProcNum
0x180021a81  lea     rcx, stru_1800320E0; pProxyInfo
0x180021a88  call    cs:__imp_NdrClientCall3
0x180021a8e  mov     rbx, rax
0x180021a91  mov     [rsp+88h+var_40], rax
0x180021a96  mov     [rsp+88h+var_48], eax
0x180021a9a  jmp     short loc_180021AC4
0x180021a9c  test    eax, eax
0x180021a9e  jle     short loc_180021AA8
0x180021aa0  movzx   eax, ax
0x180021aa3  or      eax, 80070000h
0x180021aa8  mov     ebx, eax
0x180021aaa  mov     [rsp+88h+var_48], eax
0x180021aae  mov     r8d, eax
0x180021ab1  lea     rdx, aRpcshadowThrew; "RpcShadow threw an exception: 0x%x"
0x180021ab8  mov     ecx, 8; int
0x180021abd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021ac2  xor     edi, edi
0x180021ac4  test    ebx, ebx
0x180021ac6  jns     short loc_180021AF1
0x180021ac8  lea     r9, aWinstationshad_10; "WinStationShadow"
0x180021acf  mov     r8d, ebx
0x180021ad2  lea     rdx, aRpcshadowFaile; "RpcShadow failed: 0x%x in %s"
0x180021ad9  mov     ecx, 8; int
0x180021ade  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180021ae3  mov     ecx, ebx; int
0x180021ae5  call    ?ConvertHRESULT2WIN32@@YAKJ@Z; ConvertHRESULT2WIN32(long)
0x180021aea  mov     ecx, eax
0x180021aec  jmp     loc_180021A34
0x180021af1  mov     dil, 1
0x180021af4  lea     rcx, [rsp+88h+var_38]; this
0x180021af9  call    ??1CSmartPublicBinding@@QEAA@XZ; CSmartPublicBinding::~CSmartPublicBinding(void)
0x180021afe  mov     al, dil
0x180021b01  add     rsp, 60h
0x180021b05  pop     r15
0x180021b07  pop     r14
0x180021b09  pop     rdi
0x180021b0a  pop     rsi
0x180021b0b  pop     rbx
0x180021b0c  retn
0x180030873  push    rbp
0x180030875  sub     rsp, 40h
0x180030879  mov     rbp, rdx
0x18003087c  mov     rcx, [rcx]
0x18003087f  mov     ecx, [rcx]; ExceptionCode
0x180030881  call    cs:__imp_I_RpcExceptionFilter
0x180030887  nop
0x180030888  add     rsp, 40h
0x18003088c  pop     rbp
0x18003088d  retn
```
