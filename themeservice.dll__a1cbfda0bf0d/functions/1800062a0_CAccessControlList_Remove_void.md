# CAccessControlList::Remove(void *)

- ea: `0x1800062a0`
- end: `0x18000634d`
- name: `?Remove@CAccessControlList@@QEAAJPEAX@Z`
- size: `173`
- prototype: `__int64 __fastcall(CAccessControlList *__hidden this, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000eee8`

## callees

- `0x1800034c4`
- `0x1800062a0`
- `0x180006354`
- `0x18000f9ce`

## pseudocode

```c
__int64 __fastcall CAccessControlList::Remove(CAccessControlList *this, void *a2)
{
  char *v2; // rdi
  CAccessControlList *v3; // rdx
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 *v7; // rcx
  __int64 v8; // rsi
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 result; // rax
  __int64 v12; // [rsp+30h] [rbp+8h] BYREF

  *((_QWORD *)this + 4) = a2;
  v2 = (char *)this + 8;
  v3 = this;
  for ( *((_DWORD *)this + 10) = -1; ; *((_DWORD *)this + 10) = -1 )
  {
    result = CDynamicArray<_ACCESS_ALLOWED_ACE *>::Iterate(
               (__int64)v2,
               (__int64 (__fastcall ***)(_QWORD, __int64, _QWORD))v3);
    if ( (int)result < 0 )
      break;
    v5 = *((unsigned int *)this + 10);
    if ( (int)v5 < 0 )
      break;
    v6 = *((_QWORD *)v2 + 1);
    if ( !v6 || (unsigned int)v5 >= *(_DWORD *)v2 )
      return 3221225485LL;
    v7 = (__int64 *)(v6 + 8 * v5);
    v8 = *v7;
    if ( 8 * (*(_DWORD *)v2 - (_DWORD)v5) != 8 )
      memmove_0(v7, (const void *)(v6 + 8LL * (unsigned int)(v5 + 1)), (unsigned int)(8 * (*(_DWORD *)v2 - v5) - 8));
    v9 = *((_QWORD *)v2 + 1);
    v10 = (unsigned int)(*(_DWORD *)v2 - 1);
    v12 = v8;
    *(_QWORD *)(v9 + 8 * v10) = 0;
    --*(_DWORD *)v2;
    ReleaseMemoryWorker(&v12);
    v3 = this;
  }
  return result;
}

```

## disassembly

```asm
0x1800062a0  mov     [rsp+arg_8], rbx
0x1800062a5  mov     [rsp+arg_10], rsi
0x1800062aa  push    rdi
0x1800062ab  sub     rsp, 20h
0x1800062af  mov     [rcx+20h], rdx
0x1800062b3  lea     rdi, [rcx+8]
0x1800062b7  mov     rdx, rcx
0x1800062ba  mov     dword ptr [rcx+28h], 0FFFFFFFFh
0x1800062c1  mov     rbx, rcx
0x1800062c4  jmp     short loc_18000632A
0x1800062c6  mov     edx, [rbx+28h]
0x1800062c9  test    edx, edx
0x1800062cb  js      short loc_18000633D
0x1800062cd  mov     r9, [rdi+8]
0x1800062d1  test    r9, r9
0x1800062d4  jz      short loc_180006338
0x1800062d6  mov     r8d, [rdi]
0x1800062d9  cmp     edx, r8d
0x1800062dc  jnb     short loc_180006338
0x1800062de  sub     r8d, edx
0x1800062e1  lea     rcx, [r9+rdx*8]; void *
0x1800062e5  mov     rsi, [rcx]
0x1800062e8  lea     r8d, ds:0FFFFFFFFFFFFFFF8h[r8*8]; Size
0x1800062f0  test    r8d, r8d
0x1800062f3  jz      short loc_180006301
0x1800062f5  lea     eax, [rdx+1]
0x1800062f8  lea     rdx, [r9+rax*8]; Src
0x1800062fc  call    memmove_0
0x180006301  mov     ecx, [rdi]
0x180006303  xor     edx, edx
0x180006305  mov     rax, [rdi+8]
0x180006309  dec     ecx
0x18000630b  mov     [rsp+28h+arg_0], rsi
0x180006310  mov     [rax+rcx*8], rdx
0x180006314  lea     rcx, [rsp+28h+arg_0]
0x180006319  dec     dword ptr [rdi]
0x18000631b  call    ReleaseMemoryWorker
0x180006320  mov     rdx, rbx
0x180006323  mov     dword ptr [rbx+28h], 0FFFFFFFFh
0x18000632a  mov     rcx, rdi
0x18000632d  call    ?Iterate@?$CDynamicArray@PEAU_ACCESS_ALLOWED_ACE@@@@QEAAJPEAV?$CDynamicArrayCallback@PEAU_ACCESS_ALLOWED_ACE@@@@@Z; CDynamicArray<_ACCESS_ALLOWED_ACE *>::Iterate(CDynamicArrayCallback<_ACCESS_ALLOWED_ACE *> *)
0x180006332  test    eax, eax
0x180006334  jns     short loc_1800062C6
0x180006336  jmp     short loc_18000633D
0x180006338  mov     eax, 0C000000Dh
0x18000633d  mov     rbx, [rsp+28h+arg_8]
0x180006342  mov     rsi, [rsp+28h+arg_10]
0x180006347  add     rsp, 20h
0x18000634b  pop     rdi
0x18000634c  retn
```
