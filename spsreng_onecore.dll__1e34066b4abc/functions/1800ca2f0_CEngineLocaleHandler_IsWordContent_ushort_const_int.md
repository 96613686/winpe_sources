# CEngineLocaleHandler::IsWordContent(ushort const *,int *)

- ea: `0x1800ca2f0`
- end: `0x1800ca3cb`
- name: `?IsWordContent@CEngineLocaleHandler@@UEAAJPEBGPEAH@Z`
- size: `219`
- prototype: `int(CEngineLocaleHandler *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800c91c4`
- `0x1800ca2f0`
- `0x1800cb018`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca3b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca3b8`

## pseudocode

```c
__int64 __fastcall CEngineLocaleHandler::IsWordContent(CEngineLocaleHandler *this, wchar_t *a2, int *a3)
{
  int v6; // ebp
  __int64 v7; // rax
  const unsigned __int16 *v8; // rdi
  BOOL v9; // eax
  void *v10; // rcx
  LPVOID pv[2]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v13; // [rsp+40h] [rbp-38h]

  v6 = CEngineLocaleHandler::EnsureLookupLexicon(this);
  v7 = EngineWordLexicalFormSeparator(a2);
  v8 = (const unsigned __int16 *)(v7 + 2);
  if ( !v7 )
    v8 = a2;
  v13 = 0;
  *(_OWORD *)pv = 0;
  v9 = v6 < 0
    || (*(int (__fastcall **)(_QWORD, wchar_t *, _QWORD, __int64, LPVOID *))(**((_QWORD **)this + 9) + 24LL))(
         *((_QWORD *)this + 9),
         a2,
         *((unsigned __int16 *)this + 20),
         4096,
         pv) < 0
    && (a2 == v8
     || (*(int (__fastcall **)(_QWORD, const unsigned __int16 *, _QWORD, __int64, LPVOID *))(**((_QWORD **)this + 9)
                                                                                           + 24LL))(
          *((_QWORD *)this + 9),
          v8,
          *((unsigned __int16 *)this + 20),
          4096,
          pv) < 0)
    || !v13
    || *(_DWORD *)(v13 + 16) != 24576;
  v10 = pv[1];
  *a3 = v9;
  if ( v10 )
    CoTaskMemFree(v10);
  return 0;
}

```

## disassembly

```asm
0x1800ca2f0  push    rbx
0x1800ca2f2  push    rbp
0x1800ca2f3  push    rsi
0x1800ca2f4  push    rdi
0x1800ca2f5  push    r14
0x1800ca2f7  sub     rsp, 50h
0x1800ca2fb  mov     r14, r8
0x1800ca2fe  mov     rbx, rdx
0x1800ca301  mov     rsi, rcx
0x1800ca304  call    ?EnsureLookupLexicon@CEngineLocaleHandler@@IEAAJXZ; CEngineLocaleHandler::EnsureLookupLexicon(void)
0x1800ca309  mov     rcx, rbx; Str
0x1800ca30c  mov     ebp, eax
0x1800ca30e  call    EngineWordLexicalFormSeparator
0x1800ca313  lea     rdi, [rax+2]
0x1800ca317  test    rax, rax
0x1800ca31a  jnz     short loc_1800CA31F
0x1800ca31c  mov     rdi, rbx
0x1800ca31f  xor     eax, eax
0x1800ca321  xorps   xmm0, xmm0
0x1800ca324  mov     [rsp+78h+var_38], rax
0x1800ca329  movups  xmmword ptr [rsp+78h+pv], xmm0
0x1800ca32e  test    ebp, ebp
0x1800ca330  js      short loc_1800CA3A6
0x1800ca332  mov     rcx, [rsi+48h]
0x1800ca336  lea     rdx, [rsp+78h+pv]
0x1800ca33b  movzx   r8d, word ptr [rsi+28h]
0x1800ca340  mov     ebp, 1000h
0x1800ca345  mov     [rsp+78h+var_58], rdx
0x1800ca34a  mov     r9d, ebp
0x1800ca34d  mov     rdx, rbx
0x1800ca350  mov     rax, [rcx]
0x1800ca353  mov     rax, [rax+18h]
0x1800ca357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca35c  test    eax, eax
0x1800ca35e  jns     short loc_1800CA38E
0x1800ca360  cmp     rbx, rdi
0x1800ca363  jz      short loc_1800CA3A6
0x1800ca365  mov     rcx, [rsi+48h]
0x1800ca369  lea     rdx, [rsp+78h+pv]
0x1800ca36e  movzx   r8d, word ptr [rsi+28h]
0x1800ca373  mov     r9d, ebp
0x1800ca376  mov     [rsp+78h+var_58], rdx
0x1800ca37b  mov     rdx, rdi
0x1800ca37e  mov     rax, [rcx]
0x1800ca381  mov     rax, [rax+18h]
0x1800ca385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca38a  test    eax, eax
0x1800ca38c  js      short loc_1800CA3A6
0x1800ca38e  mov     rcx, [rsp+78h+var_38]
0x1800ca393  test    rcx, rcx
0x1800ca396  jz      short loc_1800CA3A6
0x1800ca398  xor     eax, eax
0x1800ca39a  cmp     dword ptr [rcx+10h], 6000h
0x1800ca3a1  setnz   al
0x1800ca3a4  jmp     short loc_1800CA3AB
0x1800ca3a6  mov     eax, 1
0x1800ca3ab  mov     rcx, [rsp+78h+pv+8]; pv
0x1800ca3b0  mov     [r14], eax
0x1800ca3b3  test    rcx, rcx
0x1800ca3b6  jz      short loc_1800CA3BE
0x1800ca3b8  call    cs:__imp_CoTaskMemFree
0x1800ca3be  xor     eax, eax
0x1800ca3c0  add     rsp, 50h
0x1800ca3c4  pop     r14
0x1800ca3c6  pop     rdi
0x1800ca3c7  pop     rsi
0x1800ca3c8  pop     rbp
0x1800ca3c9  pop     rbx
0x1800ca3ca  retn
```
