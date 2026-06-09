# CImage::GetImageInterface(ushort const *,ulong,IDepImageSetContainer * *,IDepImageSet * *,IDepImageResolved * *)

- ea: `0x18000a814`
- end: `0x18000a940`
- name: `?GetImageInterface@CImage@@SAJPEBGKPEAPEAVIDepImageSetContainer@@PEAPEAVIDepImageSet@@PEAPEAVIDepImageResolved@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct IDepImageSetContainer **, struct IDepImageSet **, struct IDepImageResolved **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ba2c`

## callees

- `0x18000a814`
- `0x18000d5b0`
- `0x180011010`

## import_xrefs

- `ImageLib!DepImgOpenFile` at `0x18000a838`
- `ImageLib!DepImgOpenFile` at `0x18000a838`

## pseudocode

```c
__int64 __fastcall CImage::GetImageInterface(
        const unsigned __int16 *a1,
        __int64 a2,
        struct IDepImageSetContainer **a3,
        struct IDepImageSet **a4,
        struct IDepImageResolved **a5)
{
  __int64 v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // rdx
  struct IDepImageResolved **v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  char *v14; // rcx
  __int64 v15; // rcx
  _QWORD v17[3]; // [rsp+20h] [rbp-18h] BYREF

  a5 = 0;
  v17[0] = 0;
  v7 = (unsigned int)DepImgOpenFile(a1, (struct IDepImageSetContainer **)&a5);
  if ( (int)ElValidateHr_5(v7, v8, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 3633) >= 0 )
  {
    v7 = (*(unsigned int (__fastcall **)(struct IDepImageResolved **, _QWORD *))*a5)(a5, v17);
    if ( (int)ElValidateHr_5(v7, v9, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 3636) >= 0 )
    {
      if ( a3 )
      {
        v10 = a5;
        *a3 = (struct IDepImageSetContainer *)a5;
        v11 = (__int64)v10 + *((int *)v10[1] + 1) + 8;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
      }
      if ( a4 )
      {
        v12 = v17[0];
        *a4 = (struct IDepImageSet *)v17[0];
        v13 = v12 + 8 + *(int *)(*(_QWORD *)(v12 + 8) + 4LL);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
  }
  if ( a5 )
  {
    v14 = (char *)a5 + *((int *)a5[1] + 1) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))(v14);
    a5 = 0;
  }
  if ( v17[0] )
  {
    v15 = v17[0] + 8LL + *(int *)(*(_QWORD *)(v17[0] + 8LL) + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000a814  mov     rax, rsp
0x18000a817  mov     [rax+8], rbx
0x18000a81b  mov     [rax+10h], rsi
0x18000a81f  push    rdi
0x18000a820  sub     rsp, 30h
0x18000a824  and     qword ptr [rax+28h], 0
0x18000a829  lea     rdx, [rax+28h]
0x18000a82d  and     qword ptr [rax-18h], 0
0x18000a832  mov     rsi, r9
0x18000a835  mov     rdi, r8
0x18000a838  call    cs:__imp_?DepImgOpenFile@@YAJPEBGPEAPEAVIDepImageSetContainer@@@Z; DepImgOpenFile(ushort const *,IDepImageSetContainer * *)
0x18000a83f  nop     dword ptr [rax+rax+00h]
0x18000a844  mov     r9d, 0E31h
0x18000a84a  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000a851  mov     ecx, eax
0x18000a853  mov     ebx, eax
0x18000a855  call    ElValidateHr_5
0x18000a85a  test    eax, eax
0x18000a85c  js      short loc_18000A8DD
0x18000a85e  mov     rcx, [rsp+38h+arg_20]
0x18000a863  lea     rdx, [rsp+38h+var_18]
0x18000a868  mov     rax, [rcx]
0x18000a86b  mov     rax, [rax]
0x18000a86e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a873  mov     r9d, 0E34h
0x18000a879  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000a880  mov     ecx, eax
0x18000a882  mov     ebx, eax
0x18000a884  call    ElValidateHr_5
0x18000a889  test    eax, eax
0x18000a88b  js      short loc_18000A8DD
0x18000a88d  test    rdi, rdi
0x18000a890  jz      short loc_18000A8B5
0x18000a892  mov     rdx, [rsp+38h+arg_20]
0x18000a897  mov     [rdi], rdx
0x18000a89a  mov     rax, [rdx+8]
0x18000a89e  add     rdx, 8
0x18000a8a2  movsxd  rcx, dword ptr [rax+4]
0x18000a8a6  add     rcx, rdx
0x18000a8a9  mov     rax, [rcx]
0x18000a8ac  mov     rax, [rax+8]
0x18000a8b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8b5  test    rsi, rsi
0x18000a8b8  jz      short loc_18000A8DD
0x18000a8ba  mov     rdx, [rsp+38h+var_18]
0x18000a8bf  mov     [rsi], rdx
0x18000a8c2  mov     rax, [rdx+8]
0x18000a8c6  add     rdx, 8
0x18000a8ca  movsxd  rcx, dword ptr [rax+4]
0x18000a8ce  add     rcx, rdx
0x18000a8d1  mov     rax, [rcx]
0x18000a8d4  mov     rax, [rax+8]
0x18000a8d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8dd  mov     rdx, [rsp+38h+arg_20]
0x18000a8e2  test    rdx, rdx
0x18000a8e5  jz      short loc_18000A908
0x18000a8e7  mov     rax, [rdx+8]
0x18000a8eb  add     rdx, 8
0x18000a8ef  movsxd  rcx, dword ptr [rax+4]
0x18000a8f3  add     rcx, rdx
0x18000a8f6  mov     rax, [rcx]
0x18000a8f9  mov     rax, [rax+10h]
0x18000a8fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a902  and     [rsp+38h+arg_20], 0
0x18000a908  mov     rdx, [rsp+38h+var_18]
0x18000a90d  test    rdx, rdx
0x18000a910  jz      short loc_18000A92D
0x18000a912  mov     rax, [rdx+8]
0x18000a916  add     rdx, 8
0x18000a91a  movsxd  rcx, dword ptr [rax+4]
0x18000a91e  add     rcx, rdx
0x18000a921  mov     rax, [rcx]
0x18000a924  mov     rax, [rax+10h]
0x18000a928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a92d  mov     rsi, [rsp+38h+arg_8]
0x18000a932  mov     eax, ebx
0x18000a934  mov     rbx, [rsp+38h+arg_0]
0x18000a939  add     rsp, 30h
0x18000a93d  pop     rdi
0x18000a93e  retn
```
