# CUserTileStore::_GetUserNameExHelper(EXTENDED_NAME_FORMAT,ushort * *)

- ea: `0x180006d48`
- end: `0x180006e5d`
- name: `?_GetUserNameExHelper@CUserTileStore@@AEAAJW4EXTENDED_NAME_FORMAT@@PEAPEAG@Z`
- size: `277`
- prototype: `int(CUserTileStore *__hidden this, enum EXTENDED_NAME_FORMAT, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800c9f80`

## callees

- `0x180006794`
- `0x180006d48`
- `0x18003d244`
- `0x180054ad4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006dcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006dcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006da8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006e43`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006da8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006e43`
- `SspiCli!GetUserNameExW` at `0x180006d74`
- `SspiCli!GetUserNameExW` at `0x180006e15`
- `SspiCli!GetUserNameExW` at `0x180006d74`
- `SspiCli!GetUserNameExW` at `0x180006e15`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserTileStore::_GetUserNameExHelper(
        CUserTileStore *this,
        enum EXTENDED_NAME_FORMAT a2,
        unsigned __int16 **a3)
{
  int Error; // edi
  unsigned __int16 *v6; // rbx
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rsi
  size_t v9; // rax
  ULONG nSize; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+54h] [rbp+Ch]
  unsigned __int16 *v13; // [rsp+60h] [rbp+18h]

  v12 = HIDWORD(this);
  *a3 = 0;
  nSize = 0;
  if ( !GetUserNameExW(a2, 0, &nSize) )
  {
    Error = ResultFromKnownLastError();
    if ( Error != -2147024662 )
      return (unsigned int)Error;
    v13 = 0;
    CoTaskMemFree(0);
    v6 = 0;
    v13 = 0;
    if ( !is_mul_ok(nSize, 2u) )
    {
      Error = -2147024362;
      goto LABEL_14;
    }
    v7 = (unsigned __int16 *)CoTaskMemAlloc(2LL * nSize);
    v8 = v7;
    v6 = v7;
    v13 = v7;
    if ( v7 )
    {
      v9 = CTCoAllocPolicy::_CoTaskMemSize(v7);
      memset_0(v6, 0, v9);
      Error = 0;
    }
    else
    {
      Error = -2147024882;
    }
    if ( Error < 0 )
      goto LABEL_14;
    if ( GetUserNameExW(a2, v6, &nSize) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
LABEL_14:
        CoTaskMemFree(v6);
        return (unsigned int)Error;
      }
    }
    v6 = 0;
    *a3 = v8;
    goto LABEL_14;
  }
  return 0;
}

```

## disassembly

```asm
0x180006d48  mov     qword ptr [rsp+nSize], rcx
0x180006d4d  push    rbx
0x180006d4e  push    rbp
0x180006d4f  push    rsi
0x180006d50  push    rdi
0x180006d51  push    r14
0x180006d53  sub     rsp, 20h
0x180006d57  mov     r14, r8
0x180006d5a  mov     ebp, edx
0x180006d5c  mov     qword ptr [r8], 0
0x180006d63  mov     [rsp+48h+nSize], 0
0x180006d6b  lea     r8, [rsp+48h+nSize]; nSize
0x180006d70  xor     edx, edx; lpNameBuffer
0x180006d72  mov     ecx, ebp; NameFormat
0x180006d74  call    cs:__imp_GetUserNameExW
0x180006d7b  nop     dword ptr [rax+rax+00h]
0x180006d80  test    al, al
0x180006d82  jz      short loc_180006D8B
0x180006d84  xor     edi, edi
0x180006d86  jmp     loc_180006E4F
0x180006d8b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006d90  mov     edi, eax
0x180006d92  cmp     eax, 800700EAh
0x180006d97  jnz     loc_180006E4F
0x180006d9d  mov     [rsp+48h+arg_10], 0
0x180006da6  xor     ecx, ecx; pv
0x180006da8  call    cs:__imp_CoTaskMemFree
0x180006daf  nop     dword ptr [rax+rax+00h]
0x180006db4  xor     ebx, ebx
0x180006db6  mov     [rsp+48h+arg_10], rbx
0x180006dbb  mov     ecx, [rsp+48h+nSize]
0x180006dbf  lea     eax, [rbx+2]
0x180006dc2  mul     rcx
0x180006dc5  test    rdx, rdx
0x180006dc8  jnz     short loc_180006E3B
0x180006dca  mov     rcx, rax; cb
0x180006dcd  call    cs:__imp_CoTaskMemAlloc
0x180006dd4  nop     dword ptr [rax+rax+00h]
0x180006dd9  mov     rsi, rax
0x180006ddc  mov     rbx, rax
0x180006ddf  mov     [rsp+48h+arg_10], rax
0x180006de4  test    rax, rax
0x180006de7  jz      short loc_180006E02
0x180006de9  mov     rcx, rax; void *
0x180006dec  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180006df1  mov     r8, rax; Size
0x180006df4  xor     edx, edx; Val
0x180006df6  mov     rcx, rbx; void *
0x180006df9  call    memset_0
0x180006dfe  xor     edi, edi
0x180006e00  jmp     short loc_180006E07
0x180006e02  mov     edi, 8007000Eh
0x180006e07  test    edi, edi
0x180006e09  js      short loc_180006E40
0x180006e0b  lea     r8, [rsp+48h+nSize]; nSize
0x180006e10  mov     rdx, rbx; lpNameBuffer
0x180006e13  mov     ecx, ebp; NameFormat
0x180006e15  call    cs:__imp_GetUserNameExW
0x180006e1c  nop     dword ptr [rax+rax+00h]
0x180006e21  test    al, al
0x180006e23  jz      short loc_180006E29
0x180006e25  xor     edi, edi
0x180006e27  jmp     short loc_180006E34
0x180006e29  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180006e2e  mov     edi, eax
0x180006e30  test    eax, eax
0x180006e32  js      short loc_180006E40
0x180006e34  xor     ebx, ebx
0x180006e36  mov     [r14], rsi
0x180006e39  jmp     short loc_180006E40
0x180006e3b  mov     edi, 80070216h
0x180006e40  mov     rcx, rbx; pv
0x180006e43  call    cs:__imp_CoTaskMemFree
0x180006e4a  nop     dword ptr [rax+rax+00h]
0x180006e4f  mov     eax, edi
0x180006e51  add     rsp, 20h
0x180006e55  pop     r14
0x180006e57  pop     rdi
0x180006e58  pop     rsi
0x180006e59  pop     rbp
0x180006e5a  pop     rbx
0x180006e5b  retn
```
