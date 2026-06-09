# WdsImgGetSecurity

- ea: `0x180005250`
- end: `0x1800052cb`
- name: `WdsImgGetSecurity`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003c68`
- `0x180005250`
- `0x1800083b4`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall WdsImgGetSecurity(_DWORD *a1, _QWORD *a2)
{
  struct CImage *v2; // r8
  unsigned int ImageFromHandle; // ebx
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // eax
  __int64 v8; // rcx
  struct CImage *v10; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  v10 = 0;
  if ( a1 && a2 )
  {
    ImageFromHandle = CEnumImages::GetImageFromHandle(a1, &v10);
    v7 = ElValidateHr_0(ImageFromHandle, v5, v6, 0x6Bu);
    v2 = v10;
    if ( v7 >= 0 )
    {
      v8 = *((_QWORD *)v10 + 15);
      *a2 = v8;
      if ( !v8 )
        ImageFromHandle = -1056833023;
    }
  }
  else
  {
    ImageFromHandle = -2147024809;
  }
  if ( v2 )
    (*(void (__fastcall **)(struct CImage *))(*(_QWORD *)v2 + 8LL))(v2);
  return ImageFromHandle;
}

```

## disassembly

```asm
0x180005250  mov     [rsp+arg_8], rbx
0x180005255  push    rdi
0x180005256  sub     rsp, 20h
0x18000525a  xor     r8d, r8d
0x18000525d  mov     rdi, rdx
0x180005260  mov     [rsp+28h+arg_0], r8
0x180005265  test    rcx, rcx
0x180005268  jz      short loc_1800052A4
0x18000526a  test    rdx, rdx
0x18000526d  jz      short loc_1800052A4
0x18000526f  lea     rdx, [rsp+28h+arg_0]; struct CImage **
0x180005274  call    ?GetImageFromHandle@CEnumImages@@SAJPEAXPEAPEAVCImage@@@Z; CEnumImages::GetImageFromHandle(void *,CImage * *)
0x180005279  mov     r9d, 6Bh ; 'k'
0x18000527f  mov     ecx, eax
0x180005281  mov     ebx, eax
0x180005283  call    ElValidateHr_0
0x180005288  mov     r8, [rsp+28h+arg_0]
0x18000528d  test    eax, eax
0x18000528f  js      short loc_1800052A9
0x180005291  mov     rcx, [r8+78h]
0x180005295  mov     [rdi], rcx
0x180005298  test    rcx, rcx
0x18000529b  jnz     short loc_1800052A9
0x18000529d  mov     ebx, 0C1020201h
0x1800052a2  jmp     short loc_1800052A9
0x1800052a4  mov     ebx, 80070057h
0x1800052a9  test    r8, r8
0x1800052ac  jz      short loc_1800052BD
0x1800052ae  mov     rax, [r8]
0x1800052b1  mov     rcx, r8
0x1800052b4  mov     rax, [rax+8]
0x1800052b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052bd  mov     eax, ebx
0x1800052bf  mov     rbx, [rsp+28h+arg_8]
0x1800052c4  add     rsp, 20h
0x1800052c8  pop     rdi
0x1800052c9  retn
```
