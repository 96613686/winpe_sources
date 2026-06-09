# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)

- ea: `0x18000d980`
- end: `0x18000da0e`
- name: `??0TraceLoggingCorrelationVector@@QEAA@XZ`
- size: `142`
- prototype: `TraceLoggingCorrelationVector *__fastcall(TraceLoggingCorrelationVector *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d7d8`

## callees

- `0x18001c91c`
- `0x18001ff00`
- `0x180020d34`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18000d9ac`
- `RPCRT4!UuidCreate` at `0x18000d9ac`

## pseudocode

```c
TraceLoggingCorrelationVector *__fastcall TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(
        TraceLoggingCorrelationVector *this)
{
  __int64 v2; // rdx
  TraceLoggingCorrelationVector *result; // rax
  UUID Uuid; // [rsp+20h] [rbp-28h] BYREF

  *((_BYTE *)this + 130) = 65;
  Uuid = 0;
  UuidCreate(&Uuid);
  *((_BYTE *)this + 129) = 17;
  *((_QWORD *)this + 17) = 0x1300000000LL;
  memset_0(this, 0, 0x81u);
  TLV::Base64Encode<129>(&Uuid, v2, this);
  result = this;
  *((_WORD *)this + 8) = 46;
  return result;
}

```

## disassembly

```asm
0x18000d980  push    rbx
0x18000d982  sub     rsp, 40h
0x18000d986  mov     rax, cs:__security_cookie
0x18000d98d  xor     rax, rsp
0x18000d990  mov     [rsp+48h+var_18], rax
0x18000d995  mov     rbx, rcx
0x18000d998  mov     byte ptr [rcx+82h], 41h ; 'A'
0x18000d99f  xorps   xmm0, xmm0
0x18000d9a2  lea     rcx, [rsp+48h+Uuid]; Uuid
0x18000d9a7  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18000d9ac  call    cs:__imp_UuidCreate
0x18000d9b2  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x18000d9b7  mov     rax, 1300000000h
0x18000d9c1  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x18000d9c7  xor     edx, edx; Val
0x18000d9c9  mov     byte ptr [rbx+81h], 11h
0x18000d9d0  mov     r8d, 81h; Size
0x18000d9d6  mov     rcx, rbx; void *
0x18000d9d9  mov     [rbx+88h], rax
0x18000d9e0  call    memset_0
0x18000d9e5  mov     r8, rbx
0x18000d9e8  lea     rcx, [rsp+48h+Uuid]
0x18000d9ed  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x18000d9f2  mov     rax, rbx
0x18000d9f5  mov     word ptr [rbx+10h], 2Eh ; '.'
0x18000d9fb  mov     rcx, [rsp+48h+var_18]
0x18000da00  xor     rcx, rsp; StackCookie
0x18000da03  call    __security_check_cookie
0x18000da08  add     rsp, 40h
0x18000da0c  pop     rbx
0x18000da0d  retn
```
