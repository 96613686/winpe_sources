# StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)

- ea: `0x180007578`
- end: `0x180007614`
- name: `?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z`
- size: `156`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int16 **, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800012b0`

## callees

- `0x180001950`
- `0x180007578`
- `0x18000761c`

## pseudocode

```c
__int64 __fastcall StringCbCopyExW(
        unsigned __int16 *a1,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int64 *a5)
{
  HRESULT v7; // edx
  wchar_t *v8; // rcx
  size_t v9; // r9
  size_t v10; // rcx
  size_t pcchNewDestLength[5]; // [rsp+30h] [rbp-28h] BYREF

  v7 = StringExValidateDestW(a1, 0x3Au, (const size_t)a3, 0);
  if ( v7 < 0 )
  {
    *v8 = 0;
  }
  else
  {
    pcchNewDestLength[0] = v9;
    v7 = StringCopyWorkerW_0(v8, 0x3Au, pcchNewDestLength, L"\\??\\VMBusPipe\\pipe\\", 0x7FFFFFFEu);
    if ( (int)(v7 + 0x80000000) < 0 || v7 == -2147024774 )
    {
      v10 = pcchNewDestLength[0];
      if ( a4 )
        *a4 = &a1[pcchNewDestLength[0]];
      if ( a5 )
        *a5 = 2 * (58 - v10);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180007578  mov     [rsp+arg_8], rbx
0x18000757d  push    rsi
0x18000757e  push    rdi
0x18000757f  push    r14
0x180007581  sub     rsp, 40h
0x180007585  mov     rsi, [rsp+58h+arg_20]
0x18000758d  mov     r14, r9
0x180007590  xor     r9d, r9d; dwFlags
0x180007593  mov     rdi, rcx
0x180007596  lea     ebx, [r9+3Ah]
0x18000759a  mov     edx, ebx; cchDest
0x18000759c  call    StringExValidateDestW
0x1800075a1  mov     edx, eax
0x1800075a3  test    eax, eax
0x1800075a5  js      short loc_1800075FF
0x1800075a7  mov     [rsp+58h+pcchNewDestLength], r9
0x1800075ac  lea     r8, [rsp+58h+pcchNewDestLength]; pcchNewDestLength
0x1800075b1  lea     r9, aVmbuspipePipe; "\\??\\VMBusPipe\\pipe\\"
0x1800075b8  mov     [rsp+58h+cchToCopy], 7FFFFFFEh; cchToCopy
0x1800075c1  mov     edx, ebx; cchDest
0x1800075c3  call    StringCopyWorkerW_0
0x1800075c8  mov     edx, eax
0x1800075ca  mov     eax, 80000000h
0x1800075cf  lea     ecx, [rdx+rax]
0x1800075d2  test    eax, ecx
0x1800075d4  jnz     short loc_1800075DE
0x1800075d6  cmp     edx, 8007007Ah
0x1800075dc  jnz     short loc_180007604
0x1800075de  mov     rcx, [rsp+58h+pcchNewDestLength]
0x1800075e3  test    r14, r14
0x1800075e6  jz      short loc_1800075EF
0x1800075e8  lea     rax, [rdi+rcx*2]
0x1800075ec  mov     [r14], rax
0x1800075ef  test    rsi, rsi
0x1800075f2  jz      short loc_180007604
0x1800075f4  sub     rbx, rcx
0x1800075f7  add     rbx, rbx
0x1800075fa  mov     [rsi], rbx
0x1800075fd  jmp     short loc_180007604
0x1800075ff  xor     eax, eax
0x180007601  mov     [rcx], ax
0x180007604  mov     rbx, [rsp+58h+arg_8]
0x180007609  mov     eax, edx
0x18000760b  add     rsp, 40h
0x18000760f  pop     r14
0x180007611  pop     rdi
0x180007612  pop     rsi
0x180007613  retn
```
