# Microsoft::WRL::Details::MakeAndInitialize<CBitmapSourceTransformOnBitmapSource,IWICBitmapSourceTransform,IWICComponentFactory * &,IWICBitmapToneMapper *>(IWICBitmapSourceTransform * *,IWICComponentFactory * &,IWICBitmapToneMapper * &&)

- ea: `0x18003d6c0`
- end: `0x18003d7b2`
- name: `??$MakeAndInitialize@VCBitmapSourceTransformOnBitmapSource@@UIWICBitmapSourceTransform@@AEAPEAUIWICComponentFactory@@PEAUIWICBitmapToneMapper@@@Details@WRL@Microsoft@@YAJPEAPEAUIWICBitmapSourceTransform@@AEAPEAUIWICComponentFactory@@$$QEAPEAUIWICBitmapToneMapper@@@Z`
- size: `242`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003e0d0`
- `0x18003e2f0`

## callees

- `0x180036b0c`
- `0x18003be80`
- `0x18003d6c0`
- `0x180045010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CBitmapSourceTransformOnBitmapSource,IWICBitmapSourceTransform,IWICComponentFactory * &,IWICBitmapToneMapper *>(
        _QWORD *a1,
        __int64 *a2,
        __int64 *a3)
{
  CBitmapSourceTransformOnBitmapSource *v6; // rax
  CBitmapSourceTransformOnBitmapSource *v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rsi
  __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned int v13; // ebx

  *a1 = 0;
  v6 = (CBitmapSourceTransformOnBitmapSource *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v6 )
    return 2147942414LL;
  v8 = CBitmapSourceTransformOnBitmapSource::CBitmapSourceTransformOnBitmapSource(v6);
  v9 = *a3;
  v10 = *a2;
  if ( *((_QWORD *)v8 + 7) != v10 )
  {
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
    v11 = *((_QWORD *)v8 + 7);
    *((_QWORD *)v8 + 7) = v10;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  if ( *((_QWORD *)v8 + 6) != v9 )
  {
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    v12 = *((_QWORD *)v8 + 6);
    *((_QWORD *)v8 + 6) = v9;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = (**(__int64 (__fastcall ***)(CBitmapSourceTransformOnBitmapSource *, GUID *, _QWORD *))v8)(
          v8,
          &GUID_3b16811b_6a43_4ec9_b713_3d5a0c13b940,
          a1);
  (*(void (__fastcall **)(CBitmapSourceTransformOnBitmapSource *))(*(_QWORD *)v8 + 16LL))(v8);
  return v13;
}

```

## disassembly

```asm
0x18003d6c0  push    rbx
0x18003d6c2  push    rsi
0x18003d6c3  push    rdi
0x18003d6c4  push    r14
0x18003d6c6  sub     rsp, 28h
0x18003d6ca  mov     rbx, r8
0x18003d6cd  mov     rsi, rdx
0x18003d6d0  mov     r14, rcx
0x18003d6d3  mov     qword ptr [rcx], 0
0x18003d6da  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003d6e1  mov     ecx, 40h ; '@'; unsigned __int64
0x18003d6e6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003d6eb  test    rax, rax
0x18003d6ee  jnz     short loc_18003D700
0x18003d6f0  mov     eax, 8007000Eh
0x18003d6f5  add     rsp, 28h
0x18003d6f9  pop     r14
0x18003d6fb  pop     rdi
0x18003d6fc  pop     rsi
0x18003d6fd  pop     rbx
0x18003d6fe  retn
0x18003d700  mov     rcx, rax; this
0x18003d703  call    ??0CBitmapSourceTransformOnBitmapSource@@QEAA@XZ; CBitmapSourceTransformOnBitmapSource::CBitmapSourceTransformOnBitmapSource(void)
0x18003d708  mov     rdi, rax
0x18003d70b  mov     rbx, [rbx]
0x18003d70e  mov     rsi, [rsi]
0x18003d711  cmp     [rax+38h], rsi
0x18003d715  jz      short loc_18003D746
0x18003d717  test    rsi, rsi
0x18003d71a  jz      short loc_18003D72C
0x18003d71c  mov     rax, [rsi]
0x18003d71f  mov     rcx, rsi
0x18003d722  mov     rax, [rax+8]
0x18003d726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d72b  nop
0x18003d72c  mov     rcx, [rdi+38h]
0x18003d730  mov     [rdi+38h], rsi
0x18003d734  test    rcx, rcx
0x18003d737  jz      short loc_18003D746
0x18003d739  mov     rax, [rcx]
0x18003d73c  mov     rax, [rax+10h]
0x18003d740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d745  nop
0x18003d746  cmp     [rdi+30h], rbx
0x18003d74a  jz      short loc_18003D77B
0x18003d74c  test    rbx, rbx
0x18003d74f  jz      short loc_18003D761
0x18003d751  mov     rax, [rbx]
0x18003d754  mov     rcx, rbx
0x18003d757  mov     rax, [rax+8]
0x18003d75b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d760  nop
0x18003d761  mov     rcx, [rdi+30h]
0x18003d765  mov     [rdi+30h], rbx
0x18003d769  test    rcx, rcx
0x18003d76c  jz      short loc_18003D77B
0x18003d76e  mov     rax, [rcx]
0x18003d771  mov     rax, [rax+10h]
0x18003d775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d77a  nop
0x18003d77b  mov     rax, [rdi]
0x18003d77e  mov     r8, r14
0x18003d781  lea     rdx, _GUID_3b16811b_6a43_4ec9_b713_3d5a0c13b940
0x18003d788  mov     rcx, rdi
0x18003d78b  mov     rax, [rax]
0x18003d78e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d793  mov     ebx, eax
0x18003d795  mov     rcx, [rdi]
0x18003d798  mov     rax, [rcx+10h]
0x18003d79c  mov     rcx, rdi
0x18003d79f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7a4  nop
0x18003d7a5  mov     eax, ebx
0x18003d7a7  add     rsp, 28h
0x18003d7ab  pop     r14
0x18003d7ad  pop     rdi
0x18003d7ae  pop     rsi
0x18003d7af  pop     rbx
0x18003d7b0  retn
```
