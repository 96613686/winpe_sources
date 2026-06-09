# MSACredentialManagerImplementation::DeleteAccount(ushort const *,ushort const *,ushort const *)

- ea: `0x180032bc0`
- end: `0x180032c51`
- name: `?DeleteAccount@MSACredentialManagerImplementation@@UEAAJPEBG00@Z`
- size: `145`
- prototype: `int(MSACredentialManagerImplementation *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180016758`
- `0x180032bc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032be7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032be7`
- `USERENV!DeleteProfileW` at `0x180032bdd`
- `USERENV!DeleteProfileW` at `0x180032bdd`
- `samcli!NetUserDel` at `0x180032c28`
- `samcli!NetUserDel` at `0x180032c28`

## pseudocode

```c
__int64 __fastcall MSACredentialManagerImplementation::DeleteAccount(
        MSACredentialManagerImplementation *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  signed int LastError; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  signed int v10; // eax
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !DeleteProfileW(a2, 0, 0) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError != 2 )
    {
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( (v7 & 0x80000000) == 0 )
        return v7;
      v8 = 706;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
        (const char *)v7,
        v11);
      return v7;
    }
  }
  v10 = NetUserDel(a4, a3);
  v7 = v10 | 0x10000000;
  if ( v10 < 0 )
  {
    v8 = 710;
    goto LABEL_7;
  }
  return 0;
}

```

## disassembly

```asm
0x180032bc0  mov     [rsp+arg_0], rbx
0x180032bc5  mov     [rsp+arg_8], rsi
0x180032bca  push    rdi; int
0x180032bcb  sub     rsp, 20h
0x180032bcf  mov     rsi, r8
0x180032bd2  mov     rcx, rdx; lpSidString
0x180032bd5  xor     r8d, r8d; lpComputerName
0x180032bd8  xor     edx, edx; lpProfilePath
0x180032bda  mov     rdi, r9
0x180032bdd  call    cs:__imp_DeleteProfileW
0x180032be3  test    eax, eax
0x180032be5  jnz     short loc_180032C22
0x180032be7  call    cs:__imp_GetLastError
0x180032bed  mov     ebx, eax
0x180032bef  cmp     eax, 2
0x180032bf2  jz      short loc_180032C22
0x180032bf4  test    eax, eax
0x180032bf6  jle     short loc_180032C01
0x180032bf8  movzx   ebx, ax
0x180032bfb  or      ebx, 80070000h
0x180032c01  test    ebx, ebx
0x180032c03  jns     short loc_180032C1E
0x180032c05  mov     edx, 2C2h; void *
0x180032c0a  mov     rcx, [rsp+28h]; this
0x180032c0f  lea     r8, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180032c16  mov     r9d, ebx; char *
0x180032c19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032c1e  mov     eax, ebx
0x180032c20  jmp     short loc_180032C41
0x180032c22  mov     rdx, rsi; username
0x180032c25  mov     rcx, rdi; servername
0x180032c28  call    cs:__imp_NetUserDel
0x180032c2e  mov     ebx, eax
0x180032c30  or      ebx, 10000000h
0x180032c36  jge     short loc_180032C3F
0x180032c38  mov     edx, 2C6h
0x180032c3d  jmp     short loc_180032C0A
0x180032c3f  xor     eax, eax
0x180032c41  mov     rbx, [rsp+28h+arg_0]
0x180032c46  mov     rsi, [rsp+28h+arg_8]
0x180032c4b  add     rsp, 20h
0x180032c4f  pop     rdi
0x180032c50  retn
```
