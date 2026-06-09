# SMTPSendMessage(ushort *,ushort *,ushort *,ushort const *)

- ea: `0x180014e5c`
- end: `0x180014efa`
- name: `?SMTPSendMessage@@YAHPEAG00PEBG@Z`
- size: `158`
- prototype: `__int64 __fastcall(unsigned __int16 *, LPCWCH lpWideCharStr, LPCWCH, LPCWCH)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180010540`

## callees

- `0x180014b6c`
- `0x180014c50`
- `0x180014e5c`
- `0x18002924e`
- `0x180029280`

## import_xrefs

- `WS2_32!__imp_WSAStartup` at `0x180014ea4`
- `WS2_32!__imp_WSAStartup` at `0x180014ea4`
- `WS2_32!__imp_WSACleanup` at `0x180014ed4`
- `WS2_32!__imp_WSACleanup` at `0x180014ed4`

## pseudocode

```c
__int64 __fastcall SMTPSendMessage(unsigned __int16 *a1, LPCWCH lpWideCharStr, LPCWCH a3, LPCWCH a4)
{
  const unsigned __int16 *v8; // rdx
  unsigned int v10; // ebx
  unsigned __int64 v11; // rax
  WSAData WSAData; // [rsp+20h] [rbp-1D8h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( WSAStartup(0x202u, &WSAData) )
    return 0;
  v10 = 0;
  v11 = Connect(a1, v8);
  if ( v11 )
    v10 = SMTPSendEmail(v11, lpWideCharStr, a3, a4);
  WSACleanup();
  return v10;
}

```

## disassembly

```asm
0x180014e5c  push    rbx
0x180014e5e  push    rbp
0x180014e5f  push    rsi
0x180014e60  push    rdi
0x180014e61  push    r14
0x180014e63  sub     rsp, 1D0h
0x180014e6a  mov     rax, cs:__security_cookie
0x180014e71  xor     rax, rsp
0x180014e74  mov     [rsp+1F8h+var_38], rax
0x180014e7c  mov     rbp, r8
0x180014e7f  mov     rsi, rdx
0x180014e82  mov     rdi, rcx
0x180014e85  xor     edx, edx; Val
0x180014e87  mov     r8d, 198h; Size
0x180014e8d  lea     rcx, [rsp+1F8h+WSAData]; void *
0x180014e92  mov     r14, r9
0x180014e95  call    memset_0
0x180014e9a  mov     ecx, 202h; wVersionRequested
0x180014e9f  lea     rdx, [rsp+1F8h+WSAData]; lpWSAData
0x180014ea4  call    cs:__imp_WSAStartup
0x180014eaa  test    eax, eax
0x180014eac  jz      short loc_180014EB2
0x180014eae  xor     eax, eax
0x180014eb0  jmp     short loc_180014EDC
0x180014eb2  mov     rcx, rdi; unsigned __int16 *
0x180014eb5  xor     ebx, ebx
0x180014eb7  call    ?Connect@@YA_KPEBG0@Z; Connect(ushort const *,ushort const *)
0x180014ebc  test    rax, rax
0x180014ebf  jz      short loc_180014ED4
0x180014ec1  mov     r9, r14; LPCWCH
0x180014ec4  mov     r8, rbp; LPCWCH
0x180014ec7  mov     rdx, rsi; lpWideCharStr
0x180014eca  mov     rcx, rax; unsigned __int64
0x180014ecd  call    ?SMTPSendEmail@@YAH_KPEAG1PEBG@Z; SMTPSendEmail(unsigned __int64,ushort *,ushort *,ushort const *)
0x180014ed2  mov     ebx, eax
0x180014ed4  call    cs:__imp_WSACleanup
0x180014eda  mov     eax, ebx
0x180014edc  mov     rcx, [rsp+1F8h+var_38]
0x180014ee4  xor     rcx, rsp; StackCookie
0x180014ee7  call    __security_check_cookie
0x180014eec  add     rsp, 1D0h
0x180014ef3  pop     r14
0x180014ef5  pop     rdi
0x180014ef6  pop     rsi
0x180014ef7  pop     rbp
0x180014ef8  pop     rbx
0x180014ef9  retn
```
