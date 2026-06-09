# CImage::StartOperationCallback(WdsImgCopyParams *)

- ea: `0x18000c2d8`
- end: `0x18000c356`
- name: `?StartOperationCallback@CImage@@SAJPEAUWdsImgCopyParams@@@Z`
- size: `126`
- prototype: `__int64 __fastcall(struct WdsImgCopyParams *)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180008cc0`
- `0x180008e70`
- `0x1800092fc`
- `0x1800093d8`
- `0x18000c35c`

## callees

- `0x18000c2d8`
- `0x18000d5b0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall CImage::StartOperationCallback(struct WdsImgCopyParams *a1, __int64 a2)
{
  unsigned int v2; // edi
  __int64 v4; // rdx

  v2 = 0;
  if ( *((_QWORD *)a1 + 5) )
  {
    if ( !*((_DWORD *)a1 + 8)
      || (v2 = -2147023673, (int)ElValidateHr_5(2147943623LL, a2, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 3961) >= 0) )
    {
      if ( (*((unsigned int (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))a1 + 5))(2, 0, 0, *((_QWORD *)a1 + 6)) )
      {
        v2 = -2147023673;
        *((_DWORD *)a1 + 8) = 1;
        ElValidateHr_5(2147943623LL, v4, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 3973);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000c2d8  mov     [rsp+arg_0], rbx
0x18000c2dd  push    rdi
0x18000c2de  sub     rsp, 30h
0x18000c2e2  xor     edi, edi
0x18000c2e4  mov     rbx, rcx
0x18000c2e7  cmp     [rcx+28h], rdi
0x18000c2eb  jz      short loc_18000C348
0x18000c2ed  cmp     [rcx+20h], edi
0x18000c2f0  jz      short loc_18000C30F
0x18000c2f2  mov     edi, 800704C7h
0x18000c2f7  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000c2fe  mov     ecx, edi
0x18000c300  mov     r9d, 0F79h
0x18000c306  call    ElValidateHr_5
0x18000c30b  test    eax, eax
0x18000c30d  js      short loc_18000C348
0x18000c30f  mov     r9, [rbx+30h]
0x18000c313  xor     edx, edx
0x18000c315  mov     rax, [rbx+28h]
0x18000c319  xor     r8d, r8d
0x18000c31c  lea     ecx, [rdx+2]
0x18000c31f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c324  test    eax, eax
0x18000c326  jz      short loc_18000C348
0x18000c328  mov     edi, 800704C7h
0x18000c32d  mov     dword ptr [rbx+20h], 1
0x18000c334  mov     ecx, edi
0x18000c336  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000c33d  mov     r9d, 0F85h
0x18000c343  call    ElValidateHr_5
0x18000c348  mov     rbx, [rsp+38h+arg_0]
0x18000c34d  mov     eax, edi
0x18000c34f  add     rsp, 30h
0x18000c353  pop     rdi
0x18000c354  retn
```
