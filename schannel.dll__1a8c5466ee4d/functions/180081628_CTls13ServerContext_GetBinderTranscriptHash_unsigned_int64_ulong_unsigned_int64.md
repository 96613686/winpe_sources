# CTls13ServerContext::GetBinderTranscriptHash(unsigned __int64,ulong,unsigned __int64 *)

- ea: `0x180081628`
- end: `0x180081724`
- name: `?GetBinderTranscriptHash@CTls13ServerContext@@QEAAK_KKPEA_K@Z`
- size: `252`
- prototype: `unsigned int __fastcall(CTls13ServerContext *__hidden this, unsigned __int64, unsigned int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180080478`

## callees

- `0x180081628`
- `0x180091010`

## import_xrefs

- `ncrypt!SslDuplicateTranscriptHash` at `0x180081698`
- `ncrypt!SslDuplicateTranscriptHash` at `0x180081698`
- `ncrypt!SslHashHandshake` at `0x1800816db`
- `ncrypt!SslHashHandshake` at `0x1800816db`
- `ncrypt!SslCreateHandshakeHash` at `0x1800816b5`
- `ncrypt!SslCreateHandshakeHash` at `0x1800816b5`
- `ncrypt!SslFreeObject` at `0x180081704`
- `ncrypt!SslFreeObject` at `0x180081704`

## pseudocode

```c
__int64 __fastcall CTls13ServerContext::GetBinderTranscriptHash(
        CTls13ServerContext *this,
        __int64 a2,
        unsigned int a3,
        unsigned __int64 *a4)
{
  __int64 v8; // rax
  unsigned int v9; // eax
  unsigned int v10; // edi
  unsigned __int64 v11; // rcx
  unsigned __int64 v13; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 || !a4 )
    return 87;
  if ( !*((_QWORD *)this + 325) || !*((_DWORD *)this + 648) )
    return 1359;
  v8 = (*(__int64 (__fastcall **)(CTls13ServerContext *, _QWORD))(*(_QWORD *)this + 576LL))(this, 0);
  v13 = 0;
  if ( v8 )
    v9 = SslDuplicateTranscriptHash(a2, v8, &v13, 0);
  else
    v9 = SslCreateHandshakeHash(a2, &v13, *((unsigned __int16 *)this + 17), a3, 0);
  v10 = v9;
  if ( v9 || (v10 = SslHashHandshake(a2, v13, *((_QWORD *)this + 325), *((unsigned int *)this + 829), 0)) != 0 )
  {
    v11 = v13;
  }
  else
  {
    v11 = 0;
    *a4 = v13;
    v13 = 0;
  }
  if ( v11 )
    SslFreeObject(v11, 0);
  return v10;
}

```

## disassembly

```asm
0x180081628  push    rbx
0x18008162a  push    rsi
0x18008162b  push    rdi
0x18008162c  push    r14
0x18008162e  sub     rsp, 38h
0x180081632  mov     r14, r9
0x180081635  mov     edi, r8d
0x180081638  mov     rsi, rdx
0x18008163b  mov     rbx, rcx
0x18008163e  test    rdx, rdx
0x180081641  jz      loc_180081715
0x180081647  test    r9, r9
0x18008164a  jz      loc_180081715
0x180081650  cmp     qword ptr [rcx+0A28h], 0
0x180081658  jz      loc_18008170E
0x18008165e  cmp     dword ptr [rcx+0A20h], 0
0x180081665  jz      loc_18008170E
0x18008166b  mov     rax, [rcx]
0x18008166e  xor     edx, edx
0x180081670  mov     rax, [rax+240h]
0x180081677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008167c  mov     [rsp+58h+arg_8], 0
0x180081685  mov     rcx, rsi
0x180081688  test    rax, rax
0x18008168b  jz      short loc_1800816A0
0x18008168d  xor     r9d, r9d
0x180081690  lea     r8, [rsp+58h+arg_8]
0x180081695  mov     rdx, rax
0x180081698  call    cs:__imp_SslDuplicateTranscriptHash
0x18008169e  jmp     short loc_1800816BB
0x1800816a0  movzx   r8d, word ptr [rbx+22h]
0x1800816a5  lea     rdx, [rsp+58h+arg_8]
0x1800816aa  mov     r9d, edi
0x1800816ad  mov     [rsp+58h+var_38], 0
0x1800816b5  call    cs:__imp_SslCreateHandshakeHash
0x1800816bb  mov     edi, eax
0x1800816bd  test    eax, eax
0x1800816bf  jnz     short loc_1800816F8
0x1800816c1  mov     r9d, [rbx+0CF4h]
0x1800816c8  mov     rcx, rsi
0x1800816cb  mov     r8, [rbx+0A28h]
0x1800816d2  mov     rdx, [rsp+58h+arg_8]
0x1800816d7  mov     [rsp+58h+var_38], eax
0x1800816db  call    cs:__imp_SslHashHandshake
0x1800816e1  mov     edi, eax
0x1800816e3  test    eax, eax
0x1800816e5  jnz     short loc_1800816F8
0x1800816e7  mov     rax, [rsp+58h+arg_8]
0x1800816ec  xor     ecx, ecx
0x1800816ee  mov     [r14], rax
0x1800816f1  mov     [rsp+58h+arg_8], rcx
0x1800816f6  jmp     short loc_1800816FD
0x1800816f8  mov     rcx, [rsp+58h+arg_8]
0x1800816fd  test    rcx, rcx
0x180081700  jz      short loc_18008170A
0x180081702  xor     edx, edx
0x180081704  call    cs:__imp_SslFreeObject
0x18008170a  mov     eax, edi
0x18008170c  jmp     short loc_18008171A
0x18008170e  mov     eax, 54Fh
0x180081713  jmp     short loc_18008171A
0x180081715  mov     eax, 57h ; 'W'
0x18008171a  add     rsp, 38h
0x18008171e  pop     r14
0x180081720  pop     rdi
0x180081721  pop     rsi
0x180081722  pop     rbx
0x180081723  retn
```
