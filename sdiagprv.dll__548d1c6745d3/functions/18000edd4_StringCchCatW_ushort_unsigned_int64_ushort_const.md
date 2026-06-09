# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000edd4`
- end: `0x18000ee29`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `85`
- prototype: `int __fastcall(unsigned __int16 *, size_t, const unsigned __int16 *, size_t)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dc8c`
- `0x18000e7f4`
- `0x180015fa8`

## callees

- `0x18000348c`
- `0x18000edd4`
- `0x18000f098`

## pseudocode

```c
int __fastcall StringCchCatW(unsigned __int16 *a1, size_t a2, const unsigned __int16 *a3, size_t a4)
{
  int result; // eax
  size_t *v7; // r8
  __int64 v8; // r11
  size_t pcchDestLength; // [rsp+58h] [rbp+20h] BYREF

  pcchDestLength = 0;
  result = StringValidateDestAndLengthW(a1, a2, &pcchDestLength, a4);
  if ( result >= 0 )
    return StringCopyWorkerW(&a1[pcchDestLength], v8 - pcchDestLength, v7, a3, 0x7FFFFFFEu);
  return result;
}

```

## disassembly

```asm
0x18000edd4  mov     [rsp+arg_0], rbx
0x18000edd9  push    rdi
0x18000edda  sub     rsp, 30h
0x18000edde  mov     rdi, r8
0x18000ede1  mov     [rsp+38h+pcchDestLength], 0
0x18000edea  lea     r8, [rsp+38h+pcchDestLength]; pcchDestLength
0x18000edef  mov     r11, rdx
0x18000edf2  mov     rbx, rcx
0x18000edf5  call    StringValidateDestAndLengthW
0x18000edfa  test    eax, eax
0x18000edfc  js      short loc_18000EE1E
0x18000edfe  mov     rax, [rsp+38h+pcchDestLength]
0x18000ee03  mov     r9, rdi; pszSrc
0x18000ee06  sub     r11, rax
0x18000ee09  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x18000ee12  mov     rdx, r11; cchDest
0x18000ee15  lea     rcx, [rbx+rax*2]; pszDest
0x18000ee19  call    StringCopyWorkerW
0x18000ee1e  mov     rbx, [rsp+38h+arg_0]
0x18000ee23  add     rsp, 30h
0x18000ee27  pop     rdi
0x18000ee28  retn
```
