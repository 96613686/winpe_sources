# CodePageCharacterSource::CopyFrom(CharacterSource &)

- ea: `0x10041ab30`
- end: `0x10041adf1`
- name: `?CopyFrom@CodePageCharacterSource@@MEAAXAEAVCharacterSource@@@Z`
- size: `705`
- prototype: `void __fastcall(CodePageCharacterSource *__hidden this, struct CharacterSource *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x100401780`
- `0x10041ab30`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x10041ad36`
- `KERNEL32!HeapAlloc` at `0x10041ad36`
- `KERNEL32!HeapFree` at `0x10041ab7e`
- `KERNEL32!HeapFree` at `0x10041ac5c`
- `KERNEL32!HeapFree` at `0x10041ab7e`
- `KERNEL32!HeapFree` at `0x10041ac5c`

## pseudocode

```c
void __fastcall CodePageCharacterSource::CopyFrom(CodePageCharacterSource *this, struct CharacterSource *a2)
{
  void *v2; // r8
  struct IMalloc *v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rax
  void *v8; // r8
  struct IMalloc *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned int v13; // edx
  double v14; // xmm0_8
  struct IMalloc *v15; // rcx
  char *v16; // rax
  char *v17; // rcx
  char *v18; // rdx
  char *v19; // r8
  __int64 v20; // rax
  char v21; // al

  v2 = (void *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    v5 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v5 || (v5 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, void *))v5->lpVtbl->Free)(v5, v2);
    else
      HeapFree(g_hHeap, 0, v2);
  }
  v6 = *(_QWORD *)this;
  v7 = (*(__int64 (__fastcall **)(struct CharacterSource *))(*(_QWORD *)a2 + 40LL))(a2);
  (*(void (__fastcall **)(CodePageCharacterSource *, __int64))(v6 + 48))(this, v7);
  *((_BYTE *)this + 24) = *((_BYTE *)a2 + 24);
  *((_DWORD *)this + 7) = *((_DWORD *)a2 + 7);
  *((_DWORD *)this + 8) = *((_DWORD *)a2 + 8);
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 5);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 6);
  *((_QWORD *)this + 7) = *((_QWORD *)a2 + 7);
  *((_QWORD *)this + 8) = *((_QWORD *)a2 + 8);
  *((_QWORD *)this + 9) = *((_QWORD *)a2 + 9);
  *((_QWORD *)this + 10) = *((_QWORD *)a2 + 10);
  *((_DWORD *)this + 22) = *((_DWORD *)a2 + 22);
  *((_QWORD *)this + 12) = *((_QWORD *)a2 + 12);
  *((_DWORD *)this + 26) = *((_DWORD *)a2 + 26);
  *((_QWORD *)this + 14) = *((_QWORD *)a2 + 14);
  *((_DWORD *)this + 30) = *((_DWORD *)a2 + 30);
  *((_QWORD *)this + 16) = *((_QWORD *)a2 + 16);
  *((_QWORD *)a2 + 5) = 0;
  v8 = (void *)*((_QWORD *)this + 26);
  if ( v8 )
  {
    v9 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v9 || (v9 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, _QWORD))v9->lpVtbl->Free)(v9, *((_QWORD *)this + 26));
    else
      HeapFree(g_hHeap, 0, v8);
  }
  v10 = (*(__int64 (__fastcall **)(struct CharacterSource *))(*(_QWORD *)a2 + 40LL))(a2);
  v11 = *((_QWORD *)this + 6);
  v12 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 24) = v10;
  *((_DWORD *)this + 50) = *((_DWORD *)this + 7);
  LODWORD(v10) = *((_DWORD *)this + 16) - v11;
  *((_QWORD *)this + 27) = v11;
  *((_DWORD *)this + 56) = v10;
  v13 = 2 * (v11 - v12);
  *((_QWORD *)this + 29) = *((_QWORD *)this + 16);
  *((_QWORD *)this + 2) = (char *)this + 136;
  *((_QWORD *)this + 26) = v12;
  *((_DWORD *)this + 7) = v13;
  if ( v13 < 0x800 )
  {
    *((_DWORD *)this + 7) = 2048;
    v13 = 2048;
  }
  v14 = (double)(int)v13 * 0.9;
  *((_DWORD *)this + 8) = (int)v14;
  if ( v13 - (int)v14 < 0x10 )
    *((_DWORD *)this + 8) = v13 - 16;
  v15 = (struct IMalloc *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 5) = 0;
  if ( v15 || (v15 = g_pMalloc) != 0 )
    v16 = (char *)((__int64 (__fastcall *)(struct IMalloc *, _QWORD))v15->lpVtbl->Alloc)(v15, v13);
  else
    v16 = (char *)HeapAlloc(g_hHeap, 0, v13);
  v17 = v16;
  if ( !v16 )
  {
    MXRRaiseException(-2147024882);
    JUMPOUT(0x10041ADF0LL);
  }
  v18 = (char *)*((_QWORD *)this + 26);
  *((_QWORD *)this + 6) = v16;
  *((_QWORD *)this + 5) = v16;
  *((_QWORD *)this + 7) = &v16[2 * (*((_QWORD *)this + 7) - (_QWORD)v18)];
  v19 = &v16[2 * (*((_QWORD *)this + 27) - (_QWORD)v18)];
  v20 = *((_QWORD *)this + 12) - (_QWORD)v18;
  *((_QWORD *)this + 8) = v19;
  *((_QWORD *)this + 12) = &v17[2 * v20];
  *((_QWORD *)this + 14) = &v17[2 * (*((_QWORD *)this + 14) - (_QWORD)v18)];
  *((_QWORD *)this + 16) *= 2LL;
  if ( v18 && v17 < v19 )
  {
    do
    {
      v21 = *v18++;
      *(_BYTE *)(*((_QWORD *)this + 6))++ = v21;
      *(_BYTE *)(*((_QWORD *)this + 6))++ = 0;
    }
    while ( *((_QWORD *)this + 6) < *((_QWORD *)this + 8) );
  }
}

```

## disassembly

```asm
0x10041ab30  mov     [rsp+arg_0], rbx
0x10041ab35  mov     [rsp+arg_8], rsi
0x10041ab3a  push    rdi
0x10041ab3b  sub     rsp, 20h
0x10041ab3f  mov     r8, [rcx+28h]; lpMem
0x10041ab43  mov     rsi, rdx
0x10041ab46  mov     rdi, rcx
0x10041ab49  test    r8, r8
0x10041ab4c  jz      short loc_10041AB84
0x10041ab4e  mov     rcx, [rcx+8]
0x10041ab52  test    rcx, rcx
0x10041ab55  jnz     short loc_10041AB63
0x10041ab57  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041ab5e  test    rcx, rcx
0x10041ab61  jz      short loc_10041AB75
0x10041ab63  mov     rax, [rcx]
0x10041ab66  mov     rdx, r8
0x10041ab69  mov     rax, [rax+28h]
0x10041ab6d  call    cs:__guard_dispatch_icall_fptr
0x10041ab73  jmp     short loc_10041AB84
0x10041ab75  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10041ab7c  xor     edx, edx; dwFlags
0x10041ab7e  call    cs:__imp_HeapFree
0x10041ab84  mov     rax, [rsi]
0x10041ab87  mov     rcx, rsi
0x10041ab8a  mov     rbx, [rdi]
0x10041ab8d  mov     rax, [rax+28h]
0x10041ab91  call    cs:__guard_dispatch_icall_fptr
0x10041ab97  mov     rdx, rax
0x10041ab9a  mov     rcx, rdi
0x10041ab9d  mov     rax, [rbx+30h]
0x10041aba1  call    cs:__guard_dispatch_icall_fptr
0x10041aba7  movzx   eax, byte ptr [rsi+18h]
0x10041abab  xor     ebx, ebx
0x10041abad  mov     [rdi+18h], al
0x10041abb0  mov     eax, [rsi+1Ch]
0x10041abb3  mov     [rdi+1Ch], eax
0x10041abb6  mov     eax, [rsi+20h]
0x10041abb9  mov     [rdi+20h], eax
0x10041abbc  mov     rax, [rsi+28h]
0x10041abc0  mov     [rdi+28h], rax
0x10041abc4  mov     rax, [rsi+30h]
0x10041abc8  mov     [rdi+30h], rax
0x10041abcc  mov     rax, [rsi+38h]
0x10041abd0  mov     [rdi+38h], rax
0x10041abd4  mov     rax, [rsi+40h]
0x10041abd8  mov     [rdi+40h], rax
0x10041abdc  mov     rax, [rsi+48h]
0x10041abe0  mov     [rdi+48h], rax
0x10041abe4  mov     rax, [rsi+50h]
0x10041abe8  mov     [rdi+50h], rax
0x10041abec  mov     eax, [rsi+58h]
0x10041abef  mov     [rdi+58h], eax
0x10041abf2  mov     rax, [rsi+60h]
0x10041abf6  mov     [rdi+60h], rax
0x10041abfa  mov     eax, [rsi+68h]
0x10041abfd  mov     [rdi+68h], eax
0x10041ac00  mov     rax, [rsi+70h]
0x10041ac04  mov     [rdi+70h], rax
0x10041ac08  mov     eax, [rsi+78h]
0x10041ac0b  mov     [rdi+78h], eax
0x10041ac0e  mov     rax, [rsi+80h]
0x10041ac15  mov     [rdi+80h], rax
0x10041ac1c  mov     [rsi+28h], rbx
0x10041ac20  mov     r8, [rdi+0D0h]; lpMem
0x10041ac27  test    r8, r8
0x10041ac2a  jz      short loc_10041AC62
0x10041ac2c  mov     rcx, [rdi+8]
0x10041ac30  test    rcx, rcx
0x10041ac33  jnz     short loc_10041AC41
0x10041ac35  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041ac3c  test    rcx, rcx
0x10041ac3f  jz      short loc_10041AC53
0x10041ac41  mov     rax, [rcx]
0x10041ac44  mov     rdx, r8
0x10041ac47  mov     rax, [rax+28h]
0x10041ac4b  call    cs:__guard_dispatch_icall_fptr
0x10041ac51  jmp     short loc_10041AC62
0x10041ac53  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10041ac5a  xor     edx, edx; dwFlags
0x10041ac5c  call    cs:__imp_HeapFree
0x10041ac62  mov     rax, [rsi]
0x10041ac65  mov     rcx, rsi
0x10041ac68  mov     rax, [rax+28h]
0x10041ac6c  call    cs:__guard_dispatch_icall_fptr
0x10041ac72  mov     rdx, [rdi+30h]
0x10041ac76  mov     rcx, [rdi+28h]
0x10041ac7a  mov     [rdi+0C0h], rax
0x10041ac81  mov     eax, [rdi+1Ch]
0x10041ac84  mov     [rdi+0C8h], eax
0x10041ac8a  mov     eax, [rdi+40h]
0x10041ac8d  sub     eax, edx
0x10041ac8f  mov     [rdi+0D8h], rdx
0x10041ac96  mov     [rdi+0E0h], eax
0x10041ac9c  sub     edx, ecx
0x10041ac9e  mov     rax, [rdi+80h]
0x10041aca5  add     edx, edx
0x10041aca7  mov     [rdi+0E8h], rax
0x10041acae  lea     rax, [rdi+88h]
0x10041acb5  mov     [rdi+10h], rax
0x10041acb9  mov     [rdi+0D0h], rcx
0x10041acc0  mov     [rdi+1Ch], edx
0x10041acc3  cmp     edx, 800h
0x10041acc9  jnb     short loc_10041ACD7
0x10041accb  mov     dword ptr [rdi+1Ch], 800h
0x10041acd2  mov     edx, 800h
0x10041acd7  xorps   xmm0, xmm0
0x10041acda  mov     r8d, edx; dwBytes
0x10041acdd  mov     eax, edx
0x10041acdf  cvtsi2sd xmm0, r8
0x10041ace4  mulsd   xmm0, cs:__real@3feccccccccccccd
0x10041acec  cvttsd2si rcx, xmm0
0x10041acf1  sub     eax, ecx
0x10041acf3  mov     [rdi+20h], ecx
0x10041acf6  cmp     eax, 10h
0x10041acf9  jnb     short loc_10041AD02
0x10041acfb  lea     eax, [r8-10h]
0x10041acff  mov     [rdi+20h], eax
0x10041ad02  mov     rcx, [rdi+8]
0x10041ad06  mov     [rdi+28h], rbx
0x10041ad0a  test    rcx, rcx
0x10041ad0d  jz      short loc_10041AD21
0x10041ad0f  mov     rax, [rcx]
0x10041ad12  mov     rdx, r8
0x10041ad15  mov     rax, [rax+18h]
0x10041ad19  call    cs:__guard_dispatch_icall_fptr
0x10041ad1f  jmp     short loc_10041AD3C
0x10041ad21  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10041ad28  test    rcx, rcx
0x10041ad2b  jnz     short loc_10041AD0F
0x10041ad2d  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10041ad34  xor     edx, edx; dwFlags
0x10041ad36  call    cs:__imp_HeapAlloc
0x10041ad3c  mov     rcx, rax
0x10041ad3f  test    rax, rax
0x10041ad42  jz      loc_10041ADE6
0x10041ad48  mov     rdx, [rdi+0D0h]
0x10041ad4f  mov     [rdi+30h], rax
0x10041ad53  mov     [rdi+28h], rax
0x10041ad57  mov     rax, [rdi+38h]
0x10041ad5b  sub     rax, rdx
0x10041ad5e  lea     rax, [rcx+rax*2]
0x10041ad62  mov     [rdi+38h], rax
0x10041ad66  mov     rax, [rdi+0D8h]
0x10041ad6d  sub     rax, rdx
0x10041ad70  lea     r8, [rcx+rax*2]
0x10041ad74  mov     rax, [rdi+60h]
0x10041ad78  sub     rax, rdx
0x10041ad7b  mov     [rdi+40h], r8
0x10041ad7f  lea     rax, [rcx+rax*2]
0x10041ad83  mov     [rdi+60h], rax
0x10041ad87  mov     rax, [rdi+70h]
0x10041ad8b  sub     rax, rdx
0x10041ad8e  lea     rax, [rcx+rax*2]
0x10041ad92  mov     [rdi+70h], rax
0x10041ad96  mov     rax, [rdi+80h]
0x10041ad9d  add     rax, rax
0x10041ada0  mov     [rdi+80h], rax
0x10041ada7  test    rdx, rdx
0x10041adaa  jz      short loc_10041ADD6
0x10041adac  cmp     rcx, r8
0x10041adaf  jnb     short loc_10041ADD6
0x10041adb1  movzx   eax, byte ptr [rdx]
0x10041adb4  lea     rdx, [rdx+1]
0x10041adb8  mov     rcx, [rdi+30h]
0x10041adbc  mov     [rcx], al
0x10041adbe  inc     qword ptr [rdi+30h]
0x10041adc2  mov     rax, [rdi+30h]
0x10041adc6  mov     [rax], bl
0x10041adc8  inc     qword ptr [rdi+30h]
0x10041adcc  mov     rax, [rdi+30h]
0x10041add0  cmp     rax, [rdi+40h]
0x10041add4  jb      short loc_10041ADB1
0x10041add6  mov     rbx, [rsp+28h+arg_0]
0x10041addb  mov     rsi, [rsp+28h+arg_8]
0x10041ade0  add     rsp, 20h
0x10041ade4  pop     rdi
0x10041ade5  retn
0x10041ade6  mov     ecx, 8007000Eh; int
0x10041adeb  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
