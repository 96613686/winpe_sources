# WdsImgSetSecurity

- ea: `0x180005f40`
- end: `0x180005fd8`
- name: `WdsImgSetSecurity`
- size: `152`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180003c68`
- `0x180005f40`
- `0x1800083b4`
- `0x18000bfcc`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall WdsImgSetSecurity(void *a1, const unsigned __int16 *a2)
{
  __int64 ImageFromHandle; // rbx
  __int64 v4; // rdx
  __int64 v5; // r8
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  CImage *v9; // rdi
  __int64 v10; // rdx
  __int64 v11; // r8
  CImage *v13; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 && a2 )
  {
    v13 = 0;
    ImageFromHandle = (unsigned int)CEnumImages::GetImageFromHandle(a1, &v13);
    v6 = ElValidateHr_0(ImageFromHandle, v4, v5, 154);
    v9 = v13;
    if ( v6 >= 0 )
    {
      ImageFromHandle = (unsigned int)CImage::SetSecurity(v13, a2);
      ElValidateHr_0(ImageFromHandle, v10, v11, 157);
    }
    if ( v9 )
      (*(void (__fastcall **)(CImage *))(*(_QWORD *)v9 + 8LL))(v9);
    ElValidateHr_0((unsigned int)ImageFromHandle, v7, v8, 1406);
  }
  else
  {
    LODWORD(ImageFromHandle) = -2147024809;
  }
  return (unsigned int)ImageFromHandle;
}

```

## disassembly

```asm
0x180005f40  mov     rax, rsp
0x180005f43  mov     [rax+10h], rbx
0x180005f47  mov     [rax+18h], rsi
0x180005f4b  push    rdi
0x180005f4c  sub     rsp, 20h
0x180005f50  mov     rsi, rdx
0x180005f53  test    rcx, rcx
0x180005f56  jz      short loc_180005FC0
0x180005f58  test    rdx, rdx
0x180005f5b  jz      short loc_180005FC0
0x180005f5d  and     qword ptr [rax+8], 0
0x180005f62  lea     rdx, [rax+8]; struct CImage **
0x180005f66  call    ?GetImageFromHandle@CEnumImages@@SAJPEAXPEAPEAVCImage@@@Z; CEnumImages::GetImageFromHandle(void *,CImage * *)
0x180005f6b  mov     r9d, 9Ah
0x180005f71  mov     ecx, eax
0x180005f73  mov     ebx, eax
0x180005f75  call    ElValidateHr_0
0x180005f7a  mov     rdi, [rsp+28h+arg_0]
0x180005f7f  test    eax, eax
0x180005f81  js      short loc_180005F9D
0x180005f83  mov     rdx, rsi; unsigned __int16 *
0x180005f86  mov     rcx, rdi; this
0x180005f89  call    ?SetSecurity@CImage@@QEAAJPEBG@Z; CImage::SetSecurity(ushort const *)
0x180005f8e  mov     r9d, 9Dh
0x180005f94  mov     ecx, eax
0x180005f96  mov     ebx, eax
0x180005f98  call    ElValidateHr_0
0x180005f9d  test    rdi, rdi
0x180005fa0  jz      short loc_180005FB1
0x180005fa2  mov     rax, [rdi]
0x180005fa5  mov     rcx, rdi
0x180005fa8  mov     rax, [rax+8]
0x180005fac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fb1  mov     r9d, 57Eh
0x180005fb7  mov     ecx, ebx
0x180005fb9  call    ElValidateHr_0
0x180005fbe  jmp     short loc_180005FC5
0x180005fc0  mov     ebx, 80070057h
0x180005fc5  mov     rsi, [rsp+28h+arg_10]
0x180005fca  mov     eax, ebx
0x180005fcc  mov     rbx, [rsp+28h+arg_8]
0x180005fd1  add     rsp, 20h
0x180005fd5  pop     rdi
0x180005fd6  retn
```
