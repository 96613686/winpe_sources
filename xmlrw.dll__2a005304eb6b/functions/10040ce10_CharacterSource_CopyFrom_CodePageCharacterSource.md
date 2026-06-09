# CharacterSource::CopyFrom(CodePageCharacterSource &)

- ea: `0x10040ce10`
- end: `0x10040d0c2`
- name: `?CopyFrom@CharacterSource@@MEAAXAEAVCodePageCharacterSource@@@Z`
- size: `690`
- prototype: `void __fastcall(CharacterSource *__hidden this, struct CodePageCharacterSource *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x100401780`
- `0x10040ce10`
- `0x100425d50`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x10040cf5a`
- `KERNEL32!HeapAlloc` at `0x10040cf5a`
- `KERNEL32!HeapFree` at `0x10040ce5c`
- `KERNEL32!HeapFree` at `0x10040ce5c`

## pseudocode

```c
void __fastcall CharacterSource::CopyFrom(CharacterSource *this, struct CodePageCharacterSource *a2)
{
  void *v2; // r8
  struct IMalloc *v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rax
  unsigned int v8; // ebp
  __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  int v11; // eax
  unsigned int v12; // eax
  double v13; // xmm0_8
  __int64 v14; // rcx
  char *v15; // rax
  char *v16; // rbx
  __int64 v17; // rdx
  unsigned int v18; // edi
  unsigned int v19; // r15d
  unsigned int v20; // eax
  __int64 v21; // r9
  unsigned int v22; // edx
  unsigned int v23; // r10d
  unsigned __int64 v24; // rdi
  unsigned __int64 v25; // rbx
  unsigned __int64 v26; // r11
  __int64 v27; // rax
  __int64 v28; // rcx

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
  v7 = (*(__int64 (__fastcall **)(struct CodePageCharacterSource *))(*(_QWORD *)a2 + 40LL))(a2);
  (*(void (__fastcall **)(CharacterSource *, __int64))(v6 + 48))(this, v7);
  v8 = 0;
  *((_DWORD *)this + 22) = *((_DWORD *)a2 + 22);
  *((_DWORD *)this + 26) = *((_DWORD *)a2 + 26);
  *((_DWORD *)this + 30) = *((_DWORD *)a2 + 30);
  *((_QWORD *)this + 16) = *((_QWORD *)a2 + 16);
  v9 = *((_QWORD *)a2 + 5);
  v10 = *((_QWORD *)a2 + 8) - v9;
  if ( v10 )
    v11 = (*(__int64 (__fastcall **)(struct CodePageCharacterSource *, __int64, _QWORD))(*(_QWORD *)a2 + 216LL))(
            a2,
            v9,
            (unsigned int)(v10 >> 1));
  else
    v11 = 0;
  v12 = *((_DWORD *)a2 + 56) + v11;
  *((_DWORD *)this + 7) = v12;
  if ( v12 < 0x800 )
  {
    *((_DWORD *)this + 7) = 2048;
    v12 = 2048;
  }
  v13 = (double)(int)v12 * 0.9;
  *((_DWORD *)this + 8) = (int)v13;
  if ( v12 - (int)v13 < 0x10 )
    *((_DWORD *)this + 8) = v12 - 16;
  v14 = *((_QWORD *)this + 1);
  if ( v14 )
  {
    v15 = (char *)(*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v14 + 24LL))(v14, v12, v12);
  }
  else if ( g_pMalloc )
  {
    v15 = (char *)((__int64 (__fastcall *)(struct IMalloc *, _QWORD, _QWORD))g_pMalloc->lpVtbl->Alloc)(
                    g_pMalloc,
                    v12,
                    v12);
  }
  else
  {
    v15 = (char *)HeapAlloc(g_hHeap, 0, v12);
  }
  v16 = v15;
  if ( !v15 )
  {
    MXRRaiseException(-2147024882);
    JUMPOUT(0x10040D0C1LL);
  }
  *((_QWORD *)this + 5) = v15;
  v17 = *((_QWORD *)a2 + 5);
  v18 = *((_DWORD *)this + 7);
  v19 = 0;
  if ( *((_QWORD *)a2 + 6) != v17
    && (v19 = (*(__int64 (__fastcall **)(struct CodePageCharacterSource *, __int64, unsigned __int64, char *, unsigned int))(*(_QWORD *)a2 + 224LL))(
                a2,
                v17,
                (unsigned __int64)(*((_QWORD *)a2 + 8) - v17) >> 1,
                v15,
                v18)) == 0
    || (v20 = v19 + *((_DWORD *)a2 + 56), v20 > v18)
    || v20 < v19 )
  {
    MXRRaiseException(-1072894461);
    __debugbreak();
  }
  _mm_lfence();
  memmove(&v16[v19], *((const void **)a2 + 27), *((unsigned int *)a2 + 56));
  v21 = *((_QWORD *)a2 + 5);
  v22 = 0;
  v23 = v19 + *((_DWORD *)a2 + 56);
  v24 = (unsigned __int64)(*((_QWORD *)a2 + 7) - v21) >> 1;
  v25 = (unsigned __int64)(*((_QWORD *)a2 + 12) - v21) >> 1;
  v26 = (unsigned __int64)(*((_QWORD *)a2 + 14) - v21) >> 1;
  v27 = *((_QWORD *)a2 + 10);
  if ( *((_QWORD *)a2 + 9) )
    v22 = (unsigned __int64)(*((_QWORD *)a2 + 9) - v21) >> 1;
  if ( v27 )
    v8 = (unsigned __int64)(v27 - v21) >> 1;
  v28 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 6) = v28 + (unsigned int)((unsigned __int64)(*((_QWORD *)a2 + 6) - v21) >> 1);
  *((_QWORD *)this + 7) = v28 + (unsigned int)v24;
  *((_QWORD *)this + 12) = v28 + (unsigned int)v25;
  *((_QWORD *)this + 14) = v28 + (unsigned int)v26;
  *((_QWORD *)this + 8) = v28 + v23;
  *((_QWORD *)this + 9) = v28 + v22;
  *((_QWORD *)this + 10) = v28 + v8;
}

```

## disassembly

```asm
0x10040ce10  mov     [rsp+arg_10], rbx
0x10040ce15  push    rbp
0x10040ce16  push    rsi
0x10040ce17  push    r14
0x10040ce19  sub     rsp, 30h
0x10040ce1d  mov     r8, [rcx+28h]; lpMem
0x10040ce21  mov     rsi, rdx
0x10040ce24  mov     r14, rcx
0x10040ce27  test    r8, r8
0x10040ce2a  jz      short loc_10040CE62
0x10040ce2c  mov     rcx, [rcx+8]
0x10040ce30  test    rcx, rcx
0x10040ce33  jnz     short loc_10040CE41
0x10040ce35  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040ce3c  test    rcx, rcx
0x10040ce3f  jz      short loc_10040CE53
0x10040ce41  mov     rax, [rcx]
0x10040ce44  mov     rdx, r8
0x10040ce47  mov     rax, [rax+28h]
0x10040ce4b  call    cs:__guard_dispatch_icall_fptr
0x10040ce51  jmp     short loc_10040CE62
0x10040ce53  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040ce5a  xor     edx, edx; dwFlags
0x10040ce5c  call    cs:__imp_HeapFree
0x10040ce62  mov     rax, [rsi]
0x10040ce65  mov     rcx, rsi
0x10040ce68  mov     rbx, [r14]
0x10040ce6b  mov     rax, [rax+28h]
0x10040ce6f  call    cs:__guard_dispatch_icall_fptr
0x10040ce75  mov     rdx, rax
0x10040ce78  mov     rcx, r14
0x10040ce7b  mov     rax, [rbx+30h]
0x10040ce7f  call    cs:__guard_dispatch_icall_fptr
0x10040ce85  mov     eax, [rsi+58h]
0x10040ce88  xor     ebp, ebp
0x10040ce8a  mov     [r14+58h], eax
0x10040ce8e  mov     eax, [rsi+68h]
0x10040ce91  mov     [r14+68h], eax
0x10040ce95  mov     eax, [rsi+78h]
0x10040ce98  mov     [r14+78h], eax
0x10040ce9c  mov     rax, [rsi+80h]
0x10040cea3  mov     [r14+80h], rax
0x10040ceaa  mov     rdx, [rsi+28h]
0x10040ceae  mov     rcx, [rsi+40h]
0x10040ceb2  sub     rcx, rdx
0x10040ceb5  jz      short loc_10040CED2
0x10040ceb7  mov     rax, [rsi]
0x10040ceba  shr     rcx, 1
0x10040cebd  mov     r8d, ecx
0x10040cec0  mov     rcx, rsi
0x10040cec3  mov     rax, [rax+0D8h]
0x10040ceca  call    cs:__guard_dispatch_icall_fptr
0x10040ced0  jmp     short loc_10040CED4
0x10040ced2  mov     eax, ebp
0x10040ced4  add     eax, [rsi+0E0h]
0x10040ceda  mov     [r14+1Ch], eax
0x10040cede  cmp     eax, 800h
0x10040cee3  jnb     short loc_10040CEF2
0x10040cee5  mov     dword ptr [r14+1Ch], 800h
0x10040ceed  mov     eax, 800h
0x10040cef2  mov     edx, eax
0x10040cef4  xorps   xmm0, xmm0
0x10040cef7  cvtsi2sd xmm0, rdx
0x10040cefc  mulsd   xmm0, cs:__real@3feccccccccccccd
0x10040cf04  cvttsd2si rcx, xmm0
0x10040cf09  sub     eax, ecx
0x10040cf0b  mov     [r14+20h], ecx
0x10040cf0f  cmp     eax, 10h
0x10040cf12  jnb     short loc_10040CF1B
0x10040cf14  lea     eax, [rdx-10h]
0x10040cf17  mov     [r14+20h], eax
0x10040cf1b  mov     rcx, [r14+8]
0x10040cf1f  mov     r8, rdx; dwBytes
0x10040cf22  test    rcx, rcx
0x10040cf25  jz      short loc_10040CF36
0x10040cf27  mov     rax, [rcx]
0x10040cf2a  mov     rax, [rax+18h]
0x10040cf2e  call    cs:__guard_dispatch_icall_fptr
0x10040cf34  jmp     short loc_10040CF60
0x10040cf36  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x10040cf3d  test    rcx, rcx
0x10040cf40  jz      short loc_10040CF51
0x10040cf42  mov     rax, [rcx]
0x10040cf45  mov     rax, [rax+18h]
0x10040cf49  call    cs:__guard_dispatch_icall_fptr
0x10040cf4f  jmp     short loc_10040CF60
0x10040cf51  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040cf58  xor     edx, edx; dwFlags
0x10040cf5a  call    cs:__imp_HeapAlloc
0x10040cf60  mov     rbx, rax
0x10040cf63  test    rax, rax
0x10040cf66  jz      loc_10040D0B7
0x10040cf6c  mov     [r14+28h], rax
0x10040cf70  mov     rdx, [rsi+28h]
0x10040cf74  mov     [rsp+48h+arg_0], rdi
0x10040cf79  mov     edi, [r14+1Ch]
0x10040cf7d  mov     [rsp+48h+arg_8], r15
0x10040cf82  mov     r15d, ebp
0x10040cf85  cmp     [rsi+30h], rdx
0x10040cf89  jz      short loc_10040CFBA
0x10040cf8b  mov     rax, [rsi]
0x10040cf8e  mov     r9, rbx
0x10040cf91  mov     r8, [rsi+40h]
0x10040cf95  mov     rcx, rsi
0x10040cf98  sub     r8, rdx
0x10040cf9b  mov     [rsp+48h+var_28], edi
0x10040cf9f  shr     r8, 1
0x10040cfa2  mov     rax, [rax+0E0h]
0x10040cfa9  call    cs:__guard_dispatch_icall_fptr
0x10040cfaf  mov     r15d, eax
0x10040cfb2  test    eax, eax
0x10040cfb4  jz      loc_10040D0AC
0x10040cfba  mov     eax, [rsi+0E0h]
0x10040cfc0  add     eax, r15d
0x10040cfc3  cmp     eax, edi
0x10040cfc5  ja      loc_10040D0AC
0x10040cfcb  cmp     eax, r15d
0x10040cfce  jb      loc_10040D0AC
0x10040cfd4  lfence
0x10040cfd7  mov     r8d, [rsi+0E0h]; Size
0x10040cfde  mov     rdx, [rsi+0D8h]; Src
0x10040cfe5  mov     ecx, r15d
0x10040cfe8  add     rcx, rbx; void *
0x10040cfeb  call    memmove
0x10040cff0  mov     r9, [rsi+28h]
0x10040cff4  mov     edx, ebp
0x10040cff6  mov     rax, [rsi+48h]
0x10040cffa  mov     rdi, [rsi+38h]
0x10040cffe  mov     rcx, rax
0x10040d001  mov     rbx, [rsi+60h]
0x10040d005  sub     rcx, r9
0x10040d008  mov     r11, [rsi+70h]
0x10040d00c  sub     rdi, r9
0x10040d00f  mov     r8, [rsi+30h]
0x10040d013  sub     rbx, r9
0x10040d016  mov     r10d, [rsi+0E0h]
0x10040d01d  sub     r11, r9
0x10040d020  shr     rcx, 1
0x10040d023  add     r10d, r15d
0x10040d026  mov     r15, [rsp+48h+arg_8]
0x10040d02b  sub     r8, r9
0x10040d02e  shr     rdi, 1
0x10040d031  shr     rbx, 1
0x10040d034  shr     r11, 1
0x10040d037  shr     r8, 1
0x10040d03a  test    rax, rax
0x10040d03d  mov     rax, [rsi+50h]
0x10040d041  cmovnz  edx, ecx
0x10040d044  mov     rcx, rax
0x10040d047  sub     rcx, r9
0x10040d04a  shr     rcx, 1
0x10040d04d  test    rax, rax
0x10040d050  mov     eax, r8d
0x10040d053  cmovnz  ebp, ecx
0x10040d056  mov     rcx, [r14+28h]
0x10040d05a  add     rax, rcx
0x10040d05d  mov     [r14+30h], rax
0x10040d061  mov     eax, edi
0x10040d063  mov     rdi, [rsp+48h+arg_0]
0x10040d068  add     rax, rcx
0x10040d06b  mov     [r14+38h], rax
0x10040d06f  mov     eax, ebx
0x10040d071  mov     rbx, [rsp+48h+arg_10]
0x10040d076  add     rax, rcx
0x10040d079  mov     [r14+60h], rax
0x10040d07d  mov     eax, r11d
0x10040d080  add     rax, rcx
0x10040d083  mov     [r14+70h], rax
0x10040d087  mov     eax, r10d
0x10040d08a  add     rax, rcx
0x10040d08d  mov     [r14+40h], rax
0x10040d091  mov     eax, edx
0x10040d093  add     rax, rcx
0x10040d096  mov     [r14+48h], rax
0x10040d09a  mov     eax, ebp
0x10040d09c  add     rax, rcx
0x10040d09f  mov     [r14+50h], rax
0x10040d0a3  add     rsp, 30h
0x10040d0a7  pop     r14
0x10040d0a9  pop     rsi
0x10040d0aa  pop     rbp
0x10040d0ab  retn
0x10040d0ac  mov     ecx, 0C00CEE03h; int
0x10040d0b1  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040d0b6  int     3; Trap to Debugger
0x10040d0b7  mov     ecx, 8007000Eh; int
0x10040d0bc  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
