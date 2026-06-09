# CImage::VhdExportCallback(_DEP_IMAGE_COPY_CALLBACK_PARAMS *,WdsImgCopyParams *,int *)

- ea: `0x18000c46c`
- end: `0x18000c775`
- name: `?VhdExportCallback@CImage@@QEAAJPEAU_DEP_IMAGE_COPY_CALLBACK_PARAMS@@PEAUWdsImgCopyParams@@PEAH@Z`
- size: `777`
- prototype: `__int64 __fastcall(CImage *__hidden this, struct _DEP_IMAGE_COPY_CALLBACK_PARAMS *, struct WdsImgCopyParams *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d1d0`

## callees

- `0x18000c46c`
- `0x18000d5b0`
- `0x18000d6b0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c63f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c658`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c730`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c749`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c63f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c658`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c730`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c749`
- `KERNEL32!GetFileAttributesW` at `0x18000c625`
- `KERNEL32!GetFileAttributesW` at `0x18000c625`
- `WdsCommonLib!WdsAppendSuffixToFileName` at `0x18000c5cf`
- `WdsCommonLib!WdsAppendSuffixToFileName` at `0x18000c5cf`
- `WdsCommonLib!ConcatenatePaths` at `0x18000c5fe`
- `WdsCommonLib!ConcatenatePaths` at `0x18000c5fe`

## pseudocode

```c
__int64 __fastcall CImage::VhdExportCallback(
        CImage *this,
        struct _DEP_IMAGE_COPY_CALLBACK_PARAMS *a2,
        struct WdsImgCopyParams *a3,
        int *a4)
{
  unsigned int appended; // ebx
  const wchar_t *v9; // r15
  __int64 v10; // rcx
  _WORD *v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r9
  __int16 v14; // ax
  _WORD *v15; // rax
  int v16; // esi
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rcx
  _WORD *v23; // rdx
  _WORD *v24; // r9
  __int64 v25; // r8
  _WORD *v26; // rax
  LPCWSTR lpFileName; // [rsp+20h] [rbp-10h] BYREF
  void *v29; // [rsp+28h] [rbp-8h] BYREF

  appended = 0;
  v9 = 0;
  lpFileName = 0;
  v29 = 0;
  if ( !*((_DWORD *)a3 + 8)
    || (appended = -2147023673,
        (int)ElValidateHr_5(2147943623LL, a2, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 3046) >= 0) )
  {
    if ( *((_DWORD *)this + 7) == 1 )
    {
      v9 = L"Base.VHD";
    }
    else if ( *((_DWORD *)this + 7) == 3 )
    {
      v9 = L"Base.VHDX";
    }
    else
    {
      appended = -2147024883;
      if ( (int)ElValidateHr_5(2147942413LL, a2, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 3065) < 0 )
        goto LABEL_46;
    }
    *a4 = 0;
    if ( (*(_BYTE *)a2 & 1) != 0 )
    {
      v10 = *((_QWORD *)a2 + 5);
      v11 = (_WORD *)*((_QWORD *)a2 + 4);
      if ( (unsigned __int64)(v10 - 1) > 0x7FFFFFFE )
      {
        appended = -2147024809;
        if ( v10 )
          *v11 = 0;
      }
      else
      {
        v12 = 2147483646 - v10;
        v13 = *((_QWORD *)a3 + 2) - (_QWORD)v11;
        do
        {
          if ( !(v12 + v10) )
            break;
          v14 = *(_WORD *)((char *)v11 + v13);
          if ( !v14 )
            break;
          *v11++ = v14;
          --v10;
        }
        while ( v10 );
        v15 = v11 - 1;
        if ( v10 )
          v15 = v11;
        appended = v10 == 0 ? 0x8007007A : 0;
        *v15 = 0;
      }
      ElValidateHr_5(appended, v11, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 3086);
    }
    else if ( (*(_BYTE *)a2 & 2) != 0 )
    {
      *a4 = 1;
    }
    else if ( !*(_DWORD *)a2 )
    {
      v16 = 0;
      while ( 1 )
      {
        appended = WdsAppendSuffixToFileName(v9, (unsigned int)++*((_DWORD *)a3 + 15), &v29);
        if ( (unsigned int)ElValidateWin32_4(appended, v17, v18, 3111) )
          break;
        appended = ConcatenatePaths(*((_QWORD *)a3 + 1), v29, &lpFileName);
        if ( (unsigned int)ElValidateWin32_4(appended, v19, v20, 3117) )
          break;
        if ( GetFileAttributesW(lpFileName) == -1 )
          goto LABEL_33;
        if ( lpFileName )
        {
          operator delete((void *)lpFileName);
          lpFileName = 0;
        }
        if ( v29 )
        {
          operator delete(v29);
          v29 = 0;
        }
        if ( (unsigned int)++v16 >= 0xFF )
        {
          appended = -2147024865;
          if ( (int)ElValidateHr_5(2147942431LL, v21, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 3136) < 0 )
            goto LABEL_46;
LABEL_33:
          v22 = *((_QWORD *)a2 + 5);
          v23 = (_WORD *)*((_QWORD *)a2 + 4);
          if ( (unsigned __int64)(v22 - 1) > 0x7FFFFFFE )
          {
            appended = -2147024809;
            if ( v22 )
              *v23 = 0;
          }
          else
          {
            v24 = v29;
            v25 = 2147483646 - v22;
            do
            {
              if ( !(v25 + v22) )
                break;
              if ( !*v24 )
                break;
              *v23++ = *v24++;
              --v22;
            }
            while ( v22 );
            v26 = v23 - 1;
            if ( v22 )
              v26 = v23;
            appended = v22 == 0 ? 0x8007007A : 0;
            *v26 = 0;
          }
          ElValidateHr_5(appended, v23, "base\\eco\\wds\\wdsimage\\src\\image.cpp", 3146);
          goto LABEL_46;
        }
      }
      if ( (int)appended > 0 )
        appended = (unsigned __int16)appended | 0x80070000;
    }
  }
LABEL_46:
  if ( lpFileName )
  {
    operator delete((void *)lpFileName);
    lpFileName = 0;
  }
  if ( v29 )
    operator delete(v29);
  return appended;
}

```

## disassembly

```asm
0x18000c46c  mov     [rsp-28h+arg_0], rbx
0x18000c471  mov     [rsp-28h+arg_8], rsi
0x18000c476  mov     [rsp-28h+arg_18], rdi
0x18000c47b  push    rbp
0x18000c47c  push    r12
0x18000c47e  push    r13
0x18000c480  push    r14
0x18000c482  push    r15
0x18000c484  mov     rbp, rsp
0x18000c487  sub     rsp, 30h
0x18000c48b  xor     r13d, r13d
0x18000c48e  mov     rsi, r9
0x18000c491  mov     r14, r8
0x18000c494  mov     rdi, rdx
0x18000c497  mov     r12, rcx
0x18000c49a  mov     ebx, r13d
0x18000c49d  mov     r15d, r13d
0x18000c4a0  mov     [rbp+lpFileName], r13
0x18000c4a4  mov     [rbp+var_8], r13
0x18000c4a8  cmp     [r8+20h], r13d
0x18000c4ac  jz      short loc_18000C4CF
0x18000c4ae  mov     ebx, 800704C7h
0x18000c4b3  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000c4ba  mov     ecx, ebx
0x18000c4bc  mov     r9d, 0BE6h
0x18000c4c2  call    ElValidateHr_5
0x18000c4c7  test    eax, eax
0x18000c4c9  js      loc_18000C727
0x18000c4cf  cmp     dword ptr [r12+1Ch], 1
0x18000c4d5  jnz     short loc_18000C4E0
0x18000c4d7  lea     r15, aBaseVhd; "Base.VHD"
0x18000c4de  jmp     short loc_18000C512
0x18000c4e0  cmp     dword ptr [r12+1Ch], 3
0x18000c4e6  jnz     short loc_18000C4F1
0x18000c4e8  lea     r15, aBaseVhdx; "Base.VHDX"
0x18000c4ef  jmp     short loc_18000C512
0x18000c4f1  mov     ebx, 8007000Dh
0x18000c4f6  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000c4fd  mov     ecx, ebx
0x18000c4ff  mov     r9d, 0BF9h
0x18000c505  call    ElValidateHr_5
0x18000c50a  test    eax, eax
0x18000c50c  js      loc_18000C727
0x18000c512  mov     [rsi], r13d
0x18000c515  test    byte ptr [rdi], 1
0x18000c518  jz      loc_18000C5A4
0x18000c51e  mov     rcx, [rdi+28h]
0x18000c522  mov     r8d, 7FFFFFFEh
0x18000c528  mov     r9, [r14+10h]
0x18000c52c  mov     rdx, [rdi+20h]
0x18000c530  lea     rax, [rcx-1]
0x18000c534  cmp     rax, r8
0x18000c537  ja      short loc_18000C57D
0x18000c539  sub     r8, rcx
0x18000c53c  sub     r9, rdx
0x18000c53f  lea     rax, [r8+rcx]
0x18000c543  test    rax, rax
0x18000c546  jz      short loc_18000C55F
0x18000c548  movzx   eax, word ptr [r9+rdx]
0x18000c54d  test    ax, ax
0x18000c550  jz      short loc_18000C55F
0x18000c552  mov     [rdx], ax
0x18000c555  add     rdx, 2
0x18000c559  sub     rcx, 1
0x18000c55d  jnz     short loc_18000C53F
0x18000c55f  test    rcx, rcx
0x18000c562  lea     rax, [rdx-2]
0x18000c566  cmovnz  rax, rdx
0x18000c56a  neg     rcx
0x18000c56d  sbb     ebx, ebx
0x18000c56f  not     ebx
0x18000c571  and     ebx, 8007007Ah
0x18000c577  mov     [rax], r13w
0x18000c57b  jmp     short loc_18000C58B
0x18000c57d  mov     ebx, 80070057h
0x18000c582  test    rcx, rcx
0x18000c585  jz      short loc_18000C58B
0x18000c587  mov     [rdx], r13w
0x18000c58b  mov     r9d, 0C0Eh
0x18000c591  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000c598  mov     ecx, ebx
0x18000c59a  call    ElValidateHr_5
0x18000c59f  jmp     loc_18000C727
0x18000c5a4  test    byte ptr [rdi], 2
0x18000c5a7  jz      short loc_18000C5B4
0x18000c5a9  mov     dword ptr [rsi], 1
0x18000c5af  jmp     loc_18000C727
0x18000c5b4  cmp     [rdi], r13d
0x18000c5b7  jnz     loc_18000C727
0x18000c5bd  mov     esi, r13d
0x18000c5c0  inc     dword ptr [r14+3Ch]
0x18000c5c4  lea     r8, [rbp+var_8]
0x18000c5c8  mov     edx, [r14+3Ch]
0x18000c5cc  mov     rcx, r15
0x18000c5cf  call    cs:__imp_WdsAppendSuffixToFileName
0x18000c5d6  nop     dword ptr [rax+rax+00h]
0x18000c5db  mov     ecx, eax
0x18000c5dd  mov     r9d, 0C27h
0x18000c5e3  mov     ebx, eax
0x18000c5e5  call    ElValidateWin32_4
0x18000c5ea  test    eax, eax
0x18000c5ec  jnz     loc_18000C71A
0x18000c5f2  mov     rdx, [rbp+var_8]
0x18000c5f6  lea     r8, [rbp+lpFileName]
0x18000c5fa  mov     rcx, [r14+8]
0x18000c5fe  call    cs:__imp_ConcatenatePaths
0x18000c605  nop     dword ptr [rax+rax+00h]
0x18000c60a  mov     ecx, eax
0x18000c60c  mov     r9d, 0C2Dh
0x18000c612  mov     ebx, eax
0x18000c614  call    ElValidateWin32_4
0x18000c619  test    eax, eax
0x18000c61b  jnz     loc_18000C71A
0x18000c621  mov     rcx, [rbp+lpFileName]; lpFileName
0x18000c625  call    cs:__imp_GetFileAttributesW
0x18000c62c  nop     dword ptr [rax+rax+00h]
0x18000c631  cmp     eax, 0FFFFFFFFh
0x18000c634  jz      short loc_18000C697
0x18000c636  mov     rcx, [rbp+lpFileName]
0x18000c63a  test    rcx, rcx
0x18000c63d  jz      short loc_18000C64F
0x18000c63f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c646  nop     dword ptr [rax+rax+00h]
0x18000c64b  mov     [rbp+lpFileName], r13
0x18000c64f  mov     rcx, [rbp+var_8]
0x18000c653  test    rcx, rcx
0x18000c656  jz      short loc_18000C668
0x18000c658  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c65f  nop     dword ptr [rax+rax+00h]
0x18000c664  mov     [rbp+var_8], r13
0x18000c668  inc     esi
0x18000c66a  cmp     esi, 0FFh
0x18000c670  jb      loc_18000C5C0
0x18000c676  mov     ebx, 8007001Fh
0x18000c67b  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000c682  mov     ecx, ebx
0x18000c684  mov     r9d, 0C40h
0x18000c68a  call    ElValidateHr_5
0x18000c68f  test    eax, eax
0x18000c691  js      loc_18000C727
0x18000c697  mov     rcx, [rdi+28h]
0x18000c69b  mov     r8d, 7FFFFFFEh
0x18000c6a1  mov     rdx, [rdi+20h]
0x18000c6a5  lea     rax, [rcx-1]
0x18000c6a9  cmp     rax, r8
0x18000c6ac  ja      short loc_18000C6F6
0x18000c6ae  mov     r9, [rbp+var_8]
0x18000c6b2  sub     r8, rcx
0x18000c6b5  lea     rax, [r8+rcx]
0x18000c6b9  test    rax, rax
0x18000c6bc  jz      short loc_18000C6D8
0x18000c6be  movzx   eax, word ptr [r9]
0x18000c6c2  test    ax, ax
0x18000c6c5  jz      short loc_18000C6D8
0x18000c6c7  mov     [rdx], ax
0x18000c6ca  add     r9, 2
0x18000c6ce  add     rdx, 2
0x18000c6d2  sub     rcx, 1
0x18000c6d6  jnz     short loc_18000C6B5
0x18000c6d8  test    rcx, rcx
0x18000c6db  lea     rax, [rdx-2]
0x18000c6df  cmovnz  rax, rdx
0x18000c6e3  neg     rcx
0x18000c6e6  sbb     ebx, ebx
0x18000c6e8  not     ebx
0x18000c6ea  and     ebx, 8007007Ah
0x18000c6f0  mov     [rax], r13w
0x18000c6f4  jmp     short loc_18000C704
0x18000c6f6  mov     ebx, 80070057h
0x18000c6fb  test    rcx, rcx
0x18000c6fe  jz      short loc_18000C704
0x18000c700  mov     [rdx], r13w
0x18000c704  mov     r9d, 0C4Ah
0x18000c70a  lea     r8, aBaseEcoWdsWdsi_5; "base\\eco\\wds\\wdsimage\\src\\image.cp"...
0x18000c711  mov     ecx, ebx
0x18000c713  call    ElValidateHr_5
0x18000c718  jmp     short loc_18000C727
0x18000c71a  test    ebx, ebx
0x18000c71c  jle     short loc_18000C727
0x18000c71e  movzx   ebx, bx
0x18000c721  or      ebx, 80070000h
0x18000c727  mov     rcx, [rbp+lpFileName]
0x18000c72b  test    rcx, rcx
0x18000c72e  jz      short loc_18000C740
0x18000c730  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c737  nop     dword ptr [rax+rax+00h]
0x18000c73c  mov     [rbp+lpFileName], r13
0x18000c740  mov     rcx, [rbp+var_8]
0x18000c744  test    rcx, rcx
0x18000c747  jz      short loc_18000C755
0x18000c749  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c750  nop     dword ptr [rax+rax+00h]
0x18000c755  mov     rsi, [rsp+30h+arg_8]
0x18000c75a  mov     eax, ebx
0x18000c75c  mov     rbx, [rsp+30h+arg_0]
0x18000c761  mov     rdi, [rsp+30h+arg_18]
0x18000c766  add     rsp, 30h
0x18000c76a  pop     r15
0x18000c76c  pop     r14
0x18000c76e  pop     r13
0x18000c770  pop     r12
0x18000c772  pop     rbp
0x18000c773  retn
```
