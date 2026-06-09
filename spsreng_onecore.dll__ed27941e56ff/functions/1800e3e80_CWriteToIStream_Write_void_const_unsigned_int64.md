# CWriteToIStream::Write(void const *,unsigned __int64)

- ea: `0x1800e3e80`
- end: `0x1800e3f3b`
- name: `?Write@CWriteToIStream@@UEAAJPEBX_K@Z`
- size: `187`
- prototype: `__int64 __fastcall(CWriteToIStream *__hidden this, const void *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180054d28`

## callees

- `0x1800e3e80`
- `0x1800e3f44`
- `0x1800e3fbc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e3eaf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800e3eaf`

## pseudocode

```c
__int64 __fastcall CWriteToIStream::Write(CWriteToIStream *this, char *a2, unsigned __int64 a3)
{
  __int64 result; // rax
  LPVOID v7; // rax
  char *v8; // rbp
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  if ( !*((_QWORD *)this + 1) )
    return 2147500037LL;
  if ( !*((_QWORD *)this + 2) )
  {
    v7 = CoTaskMemAlloc(0x1000u);
    *((_QWORD *)this + 2) = v7;
    if ( !v7 )
      return CWriteToIStream::WriteToStream(this, a2, a3);
  }
  v10 = 0;
  result = CWriteToIStream::WriteToBuffer(this, a2, a3, &v10);
  if ( (int)result >= 0 && a3 > v10 )
  {
    v8 = &a2[v10];
    v9 = a3 - v10;
    result = CWriteToIStream::WriteToStream(this, &a2[v10], v9 & 0xFFFFFFFFFFFFF000uLL);
    if ( (int)result >= 0 )
      return CWriteToIStream::WriteToBuffer(
               this,
               &v8[v9 & 0xFFFFFFFFFFFFF000uLL],
               v9 - (v9 & 0xFFFFFFFFFFFFF000uLL),
               &v10);
  }
  return result;
}

```

## disassembly

```asm
0x1800e3e80  push    rbx
0x1800e3e82  push    rbp
0x1800e3e83  push    rsi
0x1800e3e84  push    rdi
0x1800e3e85  sub     rsp, 28h
0x1800e3e89  cmp     qword ptr [rcx+8], 0
0x1800e3e8e  mov     rdi, r8
0x1800e3e91  mov     rsi, rdx
0x1800e3e94  mov     rbx, rcx
0x1800e3e97  jnz     short loc_1800E3EA3
0x1800e3e99  mov     eax, 80004005h
0x1800e3e9e  jmp     loc_1800E3F32
0x1800e3ea3  cmp     qword ptr [rcx+10h], 0
0x1800e3ea8  jnz     short loc_1800E3ECE
0x1800e3eaa  mov     ecx, 1000h; cb
0x1800e3eaf  call    cs:__imp_CoTaskMemAlloc
0x1800e3eb5  mov     [rbx+10h], rax
0x1800e3eb9  test    rax, rax
0x1800e3ebc  jnz     short loc_1800E3ECE
0x1800e3ebe  mov     r8, rdi; unsigned __int64
0x1800e3ec1  mov     rdx, rsi; void *
0x1800e3ec4  mov     rcx, rbx; this
0x1800e3ec7  call    ?WriteToStream@CWriteToIStream@@AEAAJPEBX_K@Z; CWriteToIStream::WriteToStream(void const *,unsigned __int64)
0x1800e3ecc  jmp     short loc_1800E3F32
0x1800e3ece  lea     r9, [rsp+48h+arg_0]; unsigned __int64 *
0x1800e3ed3  mov     [rsp+48h+arg_0], 0
0x1800e3edc  mov     r8, rdi; unsigned __int64
0x1800e3edf  mov     rdx, rsi; void *
0x1800e3ee2  mov     rcx, rbx; this
0x1800e3ee5  call    ?WriteToBuffer@CWriteToIStream@@AEAAJPEBX_KPEA_K@Z; CWriteToIStream::WriteToBuffer(void const *,unsigned __int64,unsigned __int64 *)
0x1800e3eea  test    eax, eax
0x1800e3eec  js      short loc_1800E3F32
0x1800e3eee  mov     rcx, [rsp+48h+arg_0]
0x1800e3ef3  cmp     rdi, rcx
0x1800e3ef6  jbe     short loc_1800E3F32
0x1800e3ef8  lea     rbp, [rcx+rsi]
0x1800e3efc  sub     rdi, rcx
0x1800e3eff  mov     rsi, rdi
0x1800e3f02  mov     rdx, rbp; void *
0x1800e3f05  and     rsi, 0FFFFFFFFFFFFF000h
0x1800e3f0c  mov     rcx, rbx; this
0x1800e3f0f  mov     r8, rsi; unsigned __int64
0x1800e3f12  call    ?WriteToStream@CWriteToIStream@@AEAAJPEBX_K@Z; CWriteToIStream::WriteToStream(void const *,unsigned __int64)
0x1800e3f17  test    eax, eax
0x1800e3f19  js      short loc_1800E3F32
0x1800e3f1b  sub     rdi, rsi
0x1800e3f1e  lea     rdx, [rsi+rbp]; void *
0x1800e3f22  mov     r8, rdi; unsigned __int64
0x1800e3f25  lea     r9, [rsp+48h+arg_0]; unsigned __int64 *
0x1800e3f2a  mov     rcx, rbx; this
0x1800e3f2d  call    ?WriteToBuffer@CWriteToIStream@@AEAAJPEBX_KPEA_K@Z; CWriteToIStream::WriteToBuffer(void const *,unsigned __int64,unsigned __int64 *)
0x1800e3f32  add     rsp, 28h
0x1800e3f36  pop     rdi
0x1800e3f37  pop     rsi
0x1800e3f38  pop     rbp
0x1800e3f39  pop     rbx
0x1800e3f3a  retn
```
