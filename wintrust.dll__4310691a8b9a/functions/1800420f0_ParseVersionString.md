# ParseVersionString

- ea: `0x1800420f0`
- end: `0x1800421d5`
- name: `ParseVersionString`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18002ae70`
- `0x18002c090`
- `0x18002c394`
- `0x1800420f0`

## import_xrefs

- `msvcrt!_snwscanf_s` at `0x180042174`
- `msvcrt!_snwscanf_s` at `0x180042174`
- `ntdll!RtlFreeUnicodeString` at `0x1800421c5`
- `ntdll!RtlFreeUnicodeString` at `0x1800421c5`

## string_xrefs

- `0x18004212a`: `onecore\ds\security\cryptoapi\pkitrust\softpub\configciprov.cpp`

## pseudocode

```c
__int64 __fastcall ParseVersionString(__int64 a1, _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // r8d
  int v7; // [rsp+20h] [rbp-40h]
  struct _UNICODE_STRING Buffer; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  unsigned __int16 v10; // [rsp+88h] [rbp+28h] BYREF
  unsigned int v11; // [rsp+90h] [rbp+30h] BYREF
  unsigned __int16 v12; // [rsp+98h] [rbp+38h]

  v10 = 0;
  LOWORD(v11) = 0;
  v12 = 0;
  Buffer = 0;
  v3 = ParseUTF8String(a1, (__int64)&Buffer);
  v4 = v3;
  if ( v3 >= 0 )
  {
    if ( _snwscanf_s(Buffer.Buffer, (unsigned __int64)Buffer.Length >> 1, L"%hu.%hu.%hu.%hu", &v10) == 4 )
    {
      *a2 = (v12 | (((unsigned __int16)v11 | ((unsigned __int64)v10 << 16)) << 16)) << 16;
      v4 = 0;
    }
    else
    {
      v4 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x872, v5, (const char *)0xD, (unsigned int)&v11);
    }
    RtlFreeUnicodeString(&Buffer);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x868,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\pkitrust\\softpub\\configciprov.cpp",
      (const char *)(unsigned int)v3,
      v7);
  }
  return v4;
}

```

## disassembly

```asm
0x1800420f0  push    rbp
0x1800420f2  push    rbx
0x1800420f3  push    rdi
0x1800420f4  mov     rbp, rsp
0x1800420f7  sub     rsp, 60h
0x1800420fb  xor     eax, eax
0x1800420fd  mov     rdi, rdx
0x180042100  xorps   xmm0, xmm0
0x180042103  mov     [rbp+arg_8], ax
0x180042107  lea     rdx, [rbp+Buffer]
0x18004210b  mov     word ptr [rbp+arg_10], ax
0x18004210f  mov     [rbp+arg_18], ax
0x180042113  mov     [rbp+var_20], ax
0x180042117  movups  xmmword ptr [rbp+Buffer.Length], xmm0
0x18004211b  call    ParseUTF8String
0x180042120  mov     ebx, eax
0x180042122  test    eax, eax
0x180042124  jns     short loc_180042143
0x180042126  mov     rcx, [rbp+18h]; this
0x18004212a  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\pkitr"...
0x180042131  mov     r9d, eax; char *
0x180042134  mov     edx, 868h; void *
0x180042139  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004213e  jmp     loc_1800421CB
0x180042143  movzx   edx, [rbp+Buffer.Length]
0x180042147  lea     rax, [rbp+var_20]
0x18004214b  mov     rcx, [rbp+Buffer.Buffer]; Buffer
0x18004214f  lea     r9, [rbp+arg_8]
0x180042153  mov     [rsp+60h+var_30], rax
0x180042158  lea     r8, aHuHuHuHu; "%hu.%hu.%hu.%hu"
0x18004215f  lea     rax, [rbp+arg_18]
0x180042163  shr     rdx, 1; BufferCount
0x180042166  mov     [rsp+60h+var_38], rax
0x18004216b  lea     rax, [rbp+arg_10]
0x18004216f  mov     qword ptr [rsp+60h+var_40], rax; unsigned int
0x180042174  call    cs:__imp__snwscanf_s
0x18004217a  cmp     eax, 4
0x18004217d  jz      short loc_180042197
0x18004217f  mov     rcx, [rbp+18h]; this
0x180042183  mov     edx, 872h; void *
0x180042188  mov     r9d, 0Dh; char *
0x18004218e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180042193  mov     ebx, eax
0x180042195  jmp     short loc_1800421C1
0x180042197  movzx   eax, word ptr [rbp+arg_10]
0x18004219b  movzx   ecx, [rbp+arg_8]
0x18004219f  shl     rcx, 10h
0x1800421a3  or      rcx, rax
0x1800421a6  movzx   eax, [rbp+arg_18]
0x1800421aa  shl     rcx, 10h
0x1800421ae  or      rcx, rax
0x1800421b1  movzx   eax, [rbp+var_20]
0x1800421b5  shl     rcx, 10h
0x1800421b9  or      rcx, rax
0x1800421bc  mov     [rdi], rcx
0x1800421bf  xor     ebx, ebx
0x1800421c1  lea     rcx, [rbp+Buffer]; UnicodeString
0x1800421c5  call    cs:__imp_RtlFreeUnicodeString
0x1800421cb  mov     eax, ebx
0x1800421cd  add     rsp, 60h
0x1800421d1  pop     rdi
0x1800421d2  pop     rbx
0x1800421d3  pop     rbp
0x1800421d4  retn
```
