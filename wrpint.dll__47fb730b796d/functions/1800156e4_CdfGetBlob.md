# CdfGetBlob

- ea: `0x1800156e4`
- end: `0x1800157b6`
- name: `CdfGetBlob`
- size: `210`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned __int64, __int64, unsigned __int64 *, _DWORD *)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1800152e4`
- `0x1800157f4`
- `0x180015994`
- `0x180015d44`
- `0x180016750`

## callees

- `0x180015280`
- `0x1800156e4`
- `0x18001b7b0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall CdfGetBlob(
        __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        unsigned __int64 *a5,
        _DWORD *a6)
{
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rbx
  unsigned __int64 v9; // rax
  unsigned int v10; // ecx
  __int64 result; // rax
  __int64 v12; // [rsp+30h] [rbp-28h] BYREF

  v6 = *(_QWORD *)(a1 + 16);
  v12 = 0;
  if ( a2 >= *(_DWORD *)(v6 + 20) )
    goto LABEL_12;
  v7 = *(_QWORD *)(a1 + 24);
  v8 = a2;
  if ( a6 )
    *a6 = *(char *)(v7 + 8LL * a2 + 3);
  if ( a5 )
    *a5 = 0;
  v9 = *(_DWORD *)(v7 + 8LL * a2) & 0xFFFFFFLL;
  if ( v9 > a3 )
  {
    v10 = -1073741789;
    return CdfpReportErrorInner(v10);
  }
  if ( a5 )
    *a5 = v9;
  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64, __int64 *))(**(_QWORD **)(a1 + 8) + 16LL))(
             *(_QWORD *)(a1 + 8),
             *(unsigned int *)(v7 + 8LL * a2 + 4),
             *(_DWORD *)(v7 + 8LL * a2) & 0xFFFFFFLL,
             a4,
             &v12);
  if ( (int)result >= 0 && v12 != (*(_DWORD *)(v7 + 8 * v8) & 0xFFFFFFLL) )
  {
LABEL_12:
    v10 = -1073741811;
    return CdfpReportErrorInner(v10);
  }
  return result;
}

```

## disassembly

```asm
0x1800156e4  push    rbx
0x1800156e6  push    rsi
0x1800156e7  push    rdi
0x1800156e8  sub     rsp, 40h
0x1800156ec  mov     rax, cs:__security_cookie
0x1800156f3  xor     rax, rsp
0x1800156f6  mov     [rsp+58h+var_20], rax
0x1800156fb  mov     rax, [rcx+10h]
0x1800156ff  mov     r11, r9
0x180015702  mov     r9, [rsp+58h+arg_20]
0x18001570a  mov     r10, [rsp+58h+arg_28]
0x180015712  mov     [rsp+58h+var_28], 0
0x18001571b  cmp     edx, [rax+14h]
0x18001571e  jnb     short loc_180015797
0x180015720  mov     rdi, [rcx+18h]
0x180015724  mov     ebx, edx
0x180015726  test    r10, r10
0x180015729  jz      short loc_180015733
0x18001572b  movsx   eax, byte ptr [rdi+rbx*8+3]
0x180015730  mov     [r10], eax
0x180015733  test    r9, r9
0x180015736  jz      short loc_18001573F
0x180015738  mov     qword ptr [r9], 0
0x18001573f  mov     eax, [rdi+rbx*8]
0x180015742  mov     esi, 0FFFFFFh
0x180015747  and     rax, rsi
0x18001574a  cmp     rax, r8
0x18001574d  jbe     short loc_180015756
0x18001574f  mov     ecx, 0C0000023h
0x180015754  jmp     short loc_18001579C
0x180015756  test    r9, r9
0x180015759  jz      short loc_18001575E
0x18001575b  mov     [r9], rax
0x18001575e  mov     rcx, [rcx+8]
0x180015762  lea     r9, [rsp+58h+var_28]
0x180015767  mov     r8d, [rdi+rbx*8]
0x18001576b  mov     edx, [rdi+rbx*8+4]
0x18001576f  and     r8, rsi
0x180015772  mov     [rsp+58h+var_38], r9
0x180015777  mov     r9, r11
0x18001577a  mov     rax, [rcx]
0x18001577d  mov     rax, [rax+10h]
0x180015781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015786  test    eax, eax
0x180015788  js      short loc_1800157A1
0x18001578a  mov     ecx, [rdi+rbx*8]
0x18001578d  and     rcx, rsi
0x180015790  cmp     [rsp+58h+var_28], rcx
0x180015795  jz      short loc_1800157A1
0x180015797  mov     ecx, 0C000000Dh; int
0x18001579c  call    ?CdfpReportErrorInner@@YAJJH@Z; CdfpReportErrorInner(long,int)
0x1800157a1  mov     rcx, [rsp+58h+var_20]
0x1800157a6  xor     rcx, rsp; StackCookie
0x1800157a9  call    __security_check_cookie
0x1800157ae  add     rsp, 40h
0x1800157b2  pop     rdi
0x1800157b3  pop     rsi
0x1800157b4  pop     rbx
0x1800157b5  retn
```
