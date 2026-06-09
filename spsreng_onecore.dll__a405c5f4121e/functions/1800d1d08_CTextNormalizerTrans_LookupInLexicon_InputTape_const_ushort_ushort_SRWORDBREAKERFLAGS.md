# CTextNormalizerTrans::LookupInLexicon(InputTape const *,ushort,ushort *,SRWORDBREAKERFLAGS)

- ea: `0x1800d1d08`
- end: `0x1800d1e43`
- name: `?LookupInLexicon@CTextNormalizerTrans@@QEAA_NPEBVInputTape@@GPEAGW4SRWORDBREAKERFLAGS@@@Z`
- size: `315`
- prototype: `bool __high(const struct InputTape *, unsigned __int16, unsigned __int16 *, enum SRWORDBREAKERFLAGS)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1800d1e50`

## callees

- `0x180002aac`
- `0x18001474c`
- `0x1800ba7f8`
- `0x1800d1d08`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1e1a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d1e1a`

## pseudocode

```c
char __fastcall CTextNormalizerTrans::LookupInLexicon(
        __int64 a1,
        InputTape *a2,
        unsigned __int16 a3,
        unsigned __int16 *a4,
        char a5)
{
  int v6; // edi
  int v9; // r15d
  char v10; // si
  const unsigned __int16 *Str; // rax
  unsigned __int16 *v12; // rbx
  __int64 v13; // rcx
  LPVOID pv[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v16; // [rsp+40h] [rbp-48h]
  unsigned __int16 v17; // [rsp+90h] [rbp+8h] BYREF

  v6 = a3;
  if ( !*(_QWORD *)(a1 + 64) || !a2 || *((_DWORD *)a2 + 2) == 1 )
    return 0;
  v9 = *((unsigned __int16 *)a2 + 12);
  v17 = 0;
  v10 = 0;
  (*(void (__fastcall **)(InputTape *, _QWORD, unsigned __int16 *))(*(_QWORD *)a2 + 48LL))(a2, a3, &v17);
  if ( v17 > *a4 )
  {
    Str = InputTape::GetStr(a2, v6);
    v12 = CHeap::WcsDup((CHeap *)&g_heap, Str);
    if ( v12 )
    {
      if ( v17 < v9 - v6 )
        v12[v17] = 0;
      v13 = *(_QWORD *)(a1 + 64);
      v16 = 0;
      *(_OWORD *)pv = 0;
      if ( !(*(unsigned int (__fastcall **)(__int64, unsigned __int16 *, __int64, LPVOID *, bool))(*(_QWORD *)v13 + 64LL))(
              v13,
              v12,
              4099,
              pv,
              (a5 & 8) == 0) )
      {
        v10 = 1;
        *a4 = v17;
      }
      if ( pv[1] )
        CoTaskMemFree(pv[1]);
      CWinHeap::Free((CWinHeap *)&g_heap, v12);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1800d1d08  mov     r11, rsp
0x1800d1d0b  push    rbx
0x1800d1d0c  push    rbp
0x1800d1d0d  push    rsi
0x1800d1d0e  push    rdi
0x1800d1d0f  push    r14
0x1800d1d11  push    r15
0x1800d1d13  sub     rsp, 58h
0x1800d1d17  cmp     qword ptr [rcx+40h], 0
0x1800d1d1c  mov     r14, r9
0x1800d1d1f  movzx   edi, r8w
0x1800d1d23  mov     rbx, rdx
0x1800d1d26  mov     rbp, rcx
0x1800d1d29  jz      loc_1800D1E34
0x1800d1d2f  test    rdx, rdx
0x1800d1d32  jz      loc_1800D1E34
0x1800d1d38  cmp     dword ptr [rdx+8], 1
0x1800d1d3c  jz      loc_1800D1E34
0x1800d1d42  movzx   r15d, word ptr [rdx+18h]
0x1800d1d47  lea     r8, [r11+8]
0x1800d1d4b  xor     eax, eax
0x1800d1d4d  mov     rcx, rbx
0x1800d1d50  mov     [r11+8], ax
0x1800d1d55  xor     sil, sil
0x1800d1d58  mov     rax, [rdx]
0x1800d1d5b  movzx   edx, di
0x1800d1d5e  mov     rax, [rax+30h]
0x1800d1d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1d67  movzx   eax, word ptr [r14]
0x1800d1d6b  cmp     [rsp+88h+arg_0], ax
0x1800d1d73  jbe     loc_1800D1E2F
0x1800d1d79  movzx   edx, di; unsigned __int16
0x1800d1d7c  mov     rcx, rbx; this
0x1800d1d7f  call    ?GetStr@InputTape@@QEBAPEBGG@Z; InputTape::GetStr(ushort)
0x1800d1d84  mov     rdx, rax; unsigned __int16 *
0x1800d1d87  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800d1d8e  call    ?WcsDup@CHeap@@QEAAPEAGPEBG@Z; CHeap::WcsDup(ushort const *)
0x1800d1d93  mov     rbx, rax
0x1800d1d96  test    rax, rax
0x1800d1d99  jz      loc_1800D1E2F
0x1800d1d9f  movzx   eax, [rsp+88h+arg_0]
0x1800d1da7  sub     r15d, edi
0x1800d1daa  cmp     eax, r15d
0x1800d1dad  jge     short loc_1800D1DBD
0x1800d1daf  movzx   ecx, [rsp+88h+arg_0]
0x1800d1db7  xor     eax, eax
0x1800d1db9  mov     [rbx+rcx*2], ax
0x1800d1dbd  mov     rcx, [rbp+40h]
0x1800d1dc1  lea     r9, [rsp+88h+pv]
0x1800d1dc6  mov     edx, [rsp+88h+arg_20]
0x1800d1dcd  xor     eax, eax
0x1800d1dcf  shr     edx, 3
0x1800d1dd2  xorps   xmm0, xmm0
0x1800d1dd5  mov     [rsp+88h+var_48], rax
0x1800d1dda  not     edx
0x1800d1ddc  and     edx, 1
0x1800d1ddf  mov     r8d, 1003h
0x1800d1de5  movups  xmmword ptr [rsp+88h+pv], xmm0
0x1800d1dea  mov     rax, [rcx]
0x1800d1ded  mov     [rsp+88h+var_68], edx
0x1800d1df1  mov     rdx, rbx
0x1800d1df4  mov     rax, [rax+40h]
0x1800d1df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1dfd  test    eax, eax
0x1800d1dff  jnz     short loc_1800D1E10
0x1800d1e01  movzx   eax, [rsp+88h+arg_0]
0x1800d1e09  mov     sil, 1
0x1800d1e0c  mov     [r14], ax
0x1800d1e10  mov     rcx, [rsp+88h+pv+8]; pv
0x1800d1e15  test    rcx, rcx
0x1800d1e18  jz      short loc_1800D1E20
0x1800d1e1a  call    cs:__imp_CoTaskMemFree
0x1800d1e20  mov     rdx, rbx; void *
0x1800d1e23  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800d1e2a  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800d1e2f  mov     al, sil
0x1800d1e32  jmp     short loc_1800D1E36
0x1800d1e34  xor     al, al
0x1800d1e36  add     rsp, 58h
0x1800d1e3a  pop     r15
0x1800d1e3c  pop     r14
0x1800d1e3e  pop     rdi
0x1800d1e3f  pop     rsi
0x1800d1e40  pop     rbp
0x1800d1e41  pop     rbx
0x1800d1e42  retn
```
