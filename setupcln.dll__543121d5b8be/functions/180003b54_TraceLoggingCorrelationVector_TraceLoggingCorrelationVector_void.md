# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)

- ea: `0x180003b54`
- end: `0x180003be2`
- name: `??0TraceLoggingCorrelationVector@@QEAA@XZ`
- size: `142`
- prototype: `TraceLoggingCorrelationVector *__fastcall(TraceLoggingCorrelationVector *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005080`

## callees

- `0x180003648`
- `0x1800131a2`
- `0x1800131e0`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180003b80`
- `RPCRT4!UuidCreate` at `0x180003b80`

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
0x180003b54  push    rbx
0x180003b56  sub     rsp, 40h
0x180003b5a  mov     rax, cs:__security_cookie
0x180003b61  xor     rax, rsp
0x180003b64  mov     [rsp+48h+var_18], rax
0x180003b69  mov     rbx, rcx
0x180003b6c  mov     byte ptr [rcx+82h], 41h ; 'A'
0x180003b73  xorps   xmm0, xmm0
0x180003b76  lea     rcx, [rsp+48h+Uuid]; Uuid
0x180003b7b  movups  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x180003b80  call    cs:__imp_UuidCreate
0x180003b86  movaps  xmm0, xmmword ptr [rsp+48h+Uuid.Data1]
0x180003b8b  mov     rax, 1300000000h
0x180003b95  movdqa  xmmword ptr [rsp+48h+Uuid.Data1], xmm0
0x180003b9b  xor     edx, edx; Val
0x180003b9d  mov     byte ptr [rbx+81h], 11h
0x180003ba4  mov     r8d, 81h; Size
0x180003baa  mov     rcx, rbx; void *
0x180003bad  mov     [rbx+88h], rax
0x180003bb4  call    memset_0
0x180003bb9  mov     r8, rbx
0x180003bbc  lea     rcx, [rsp+48h+Uuid]
0x180003bc1  call    ??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z; TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])
0x180003bc6  mov     rax, rbx
0x180003bc9  mov     word ptr [rbx+10h], 2Eh ; '.'
0x180003bcf  mov     rcx, [rsp+48h+var_18]
0x180003bd4  xor     rcx, rsp; StackCookie
0x180003bd7  call    __security_check_cookie
0x180003bdc  add     rsp, 40h
0x180003be0  pop     rbx
0x180003be1  retn
```
