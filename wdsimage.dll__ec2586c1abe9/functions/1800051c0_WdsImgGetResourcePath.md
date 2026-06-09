# WdsImgGetResourcePath

- ea: `0x1800051c0`
- end: `0x18000523b`
- name: `WdsImgGetResourcePath`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180003c68`
- `0x1800051c0`
- `0x1800083b4`
- `0x18000ab54`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall WdsImgGetResourcePath(void *a1, _QWORD *a2)
{
  CImage *v2; // rbx
  __int64 ImageFromHandle; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // eax
  CImage *v9; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  v9 = 0;
  if ( a1 && a2 )
  {
    ImageFromHandle = (unsigned int)CEnumImages::GetImageFromHandle(a1, &v9);
    v7 = ElValidateHr_0(ImageFromHandle, v5, v6, 62);
    v2 = v9;
    if ( v7 >= 0 )
      *a2 = CImage::GetResourceFilePath(v9);
  }
  else
  {
    LODWORD(ImageFromHandle) = -2147024809;
  }
  if ( v2 )
    (*(void (__fastcall **)(CImage *))(*(_QWORD *)v2 + 8LL))(v2);
  return (unsigned int)ImageFromHandle;
}

```

## disassembly

```asm
0x1800051c0  mov     rax, rsp
0x1800051c3  mov     [rax+10h], rbx
0x1800051c7  mov     [rax+18h], rsi
0x1800051cb  push    rdi
0x1800051cc  sub     rsp, 20h
0x1800051d0  xor     ebx, ebx
0x1800051d2  mov     rsi, rdx
0x1800051d5  mov     [rax+8], rbx
0x1800051d9  test    rcx, rcx
0x1800051dc  jz      short loc_18000520F
0x1800051de  test    rdx, rdx
0x1800051e1  jz      short loc_18000520F
0x1800051e3  lea     rdx, [rax+8]; struct CImage **
0x1800051e7  call    ?GetImageFromHandle@CEnumImages@@SAJPEAXPEAPEAVCImage@@@Z; CEnumImages::GetImageFromHandle(void *,CImage * *)
0x1800051ec  lea     r9d, [rbx+3Eh]
0x1800051f0  mov     ecx, eax
0x1800051f2  mov     edi, eax
0x1800051f4  call    ElValidateHr_0
0x1800051f9  mov     rbx, [rsp+28h+arg_0]
0x1800051fe  test    eax, eax
0x180005200  js      short loc_180005214
0x180005202  mov     rcx, rbx; this
0x180005205  call    ?GetResourceFilePath@CImage@@QEAAPEAGXZ; CImage::GetResourceFilePath(void)
0x18000520a  mov     [rsi], rax
0x18000520d  jmp     short loc_180005214
0x18000520f  mov     edi, 80070057h
0x180005214  test    rbx, rbx
0x180005217  jz      short loc_180005228
0x180005219  mov     rax, [rbx]
0x18000521c  mov     rcx, rbx
0x18000521f  mov     rax, [rax+8]
0x180005223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005228  mov     rbx, [rsp+28h+arg_8]
0x18000522d  mov     eax, edi
0x18000522f  mov     rsi, [rsp+28h+arg_10]
0x180005234  add     rsp, 20h
0x180005238  pop     rdi
0x180005239  retn
```
