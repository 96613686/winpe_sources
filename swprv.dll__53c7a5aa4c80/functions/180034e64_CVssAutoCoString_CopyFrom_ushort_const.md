# CVssAutoCoString::CopyFrom(ushort const *)

- ea: `0x180034e64`
- end: `0x180034ed3`
- name: `?CopyFrom@CVssAutoCoString@@QEAA_NPEBG@Z`
- size: `111`
- prototype: `bool __fastcall(LPVOID *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180034f3c`
- `0x18003649c`
- `0x180036614`

## callees

- `0x180007604`
- `0x180034e64`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034e76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180034e76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034e9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034e9e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall CVssAutoCoString::CopyFrom(LPVOID *this, const unsigned __int16 *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rcx
  unsigned __int16 *v6; // rax

  CoTaskMemFree(*this);
  *this = 0;
  if ( a2 )
  {
    v4 = -1;
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
    v6 = (unsigned __int16 *)CoTaskMemAlloc(2 * v5 + 2);
    *this = v6;
    if ( v6 )
    {
      do
        ++v4;
      while ( a2[v4] );
      StringCchCopyW(v6, v4 + 1, a2);
    }
  }
  return *this != 0;
}

```

## disassembly

```asm
0x180034e64  push    rbx
0x180034e66  push    rbp
0x180034e67  push    rsi
0x180034e68  push    rdi
0x180034e69  sub     rsp, 28h
0x180034e6d  mov     rbx, rcx
0x180034e70  mov     rsi, rdx
0x180034e73  mov     rcx, [rcx]; pv
0x180034e76  call    cs:__imp_CoTaskMemFree
0x180034e7c  xor     ebp, ebp
0x180034e7e  mov     [rbx], rbp
0x180034e81  test    rsi, rsi
0x180034e84  jz      short loc_180034EC4
0x180034e86  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180034e8a  mov     rcx, rdi
0x180034e8d  inc     rcx
0x180034e90  cmp     [rsi+rcx*2], bp
0x180034e94  jnz     short loc_180034E8D
0x180034e96  lea     rcx, ds:2[rcx*2]; cb
0x180034e9e  call    cs:__imp_CoTaskMemAlloc
0x180034ea4  mov     [rbx], rax
0x180034ea7  test    rax, rax
0x180034eaa  jz      short loc_180034EC4
0x180034eac  inc     rdi
0x180034eaf  cmp     [rsi+rdi*2], bp
0x180034eb3  jnz     short loc_180034EAC
0x180034eb5  lea     rdx, [rdi+1]; unsigned __int64
0x180034eb9  mov     r8, rsi; unsigned __int16 *
0x180034ebc  mov     rcx, rax; unsigned __int16 *
0x180034ebf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180034ec4  cmp     [rbx], rbp
0x180034ec7  setnz   al
0x180034eca  add     rsp, 28h
0x180034ece  pop     rdi
0x180034ecf  pop     rsi
0x180034ed0  pop     rbp
0x180034ed1  pop     rbx
0x180034ed2  retn
```
