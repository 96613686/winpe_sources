# p9fs::File::SetAttr(uint,p9fs::StatResult const &)

- ea: `0x1800214d0`
- end: `0x180021720`
- name: `?SetAttr@File@p9fs@@UEAAJIAEBUStatResult@2@@Z`
- size: `592`
- prototype: `__int64 __fastcall(p9fs::File *__hidden this, unsigned int, const struct p9fs::StatResult *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x180004120`
- `0x180020520`
- `0x1800214d0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002158c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800215f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800216da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800216f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002158c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800215f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800216da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800216f8`
- `lxutil!LxUtilFsTruncate` at `0x18002156c`
- `lxutil!LxUtilFsTruncate` at `0x18002156c`
- `lxutil!LxUtilFsSetTimes` at `0x1800216ba`
- `lxutil!LxUtilFsSetTimes` at `0x1800216ba`
- `lxutil!LxUtilFsChmod` at `0x180021618`
- `lxutil!LxUtilFsChmod` at `0x180021618`
- `lxutil!LxUtilFsUpdateLxAttributes` at `0x1800215d2`
- `lxutil!LxUtilFsUpdateLxAttributes` at `0x1800215d2`

## pseudocode

```c
__int64 __fastcall p9fs::File::SetAttr(p9fs::File *this, __int16 a2, const struct p9fs::StatResult *a3)
{
  __int64 v5; // rdx
  unsigned int v8; // ecx
  bool v9; // r14
  __int64 v10; // r8
  unsigned int v11; // esi
  int v12; // esi
  __int64 v13; // rdx
  __int64 v14; // r8
  unsigned int updated; // r14d
  __int64 v16; // rcx
  unsigned int v17; // ebx
  _BYTE v18[8]; // [rsp+20h] [rbp-50h] BYREF
  HANDLE hObject; // [rsp+28h] [rbp-48h]
  __int64 v20; // [rsp+30h] [rbp-40h] BYREF
  __int64 v21; // [rsp+38h] [rbp-38h]
  __int64 v22; // [rsp+40h] [rbp-30h] BYREF
  __int64 v23; // [rsp+48h] [rbp-28h]
  _QWORD v24[2]; // [rsp+50h] [rbp-20h] BYREF

  v5 = *((_QWORD *)this + 9);
  if ( (*(_BYTE *)(v5 + 48) & 1) != 0 )
    return 4294967266LL;
  v8 = (a2 & 8) != 0 ? 1048962 : 1048960;
  v9 = (*(_BYTE *)(v5 + 48) & 4) != 0 && (*(_DWORD *)(v5 + 40) & 0x1000) != 0;
  v10 = v8 | 0x18;
  if ( !v9 )
    v10 = v8;
  p9fs::File::OpenHandle(this, v18, v10);
  if ( !v18[0] )
    return (unsigned int)hObject;
  if ( (a2 & 8) != 0 )
  {
    v11 = LxUtilFsTruncate(hObject, *((_QWORD *)a3 + 4));
    if ( v11 )
      goto LABEL_13;
  }
  if ( v9 && (a2 & 7) != 0 )
  {
    if ( (a2 & 1) != 0 )
      v12 = *(_DWORD *)a3;
    else
      v12 = -1;
    if ( (a2 & 2) != 0 )
      v13 = *((unsigned int *)a3 + 1);
    else
      v13 = 0xFFFFFFFFLL;
    if ( (a2 & 4) != 0 )
      v14 = *((unsigned int *)a3 + 2);
    else
      v14 = 0xFFFFFFFFLL;
    updated = LxUtilFsUpdateLxAttributes(hObject, v13, v14);
    if ( updated )
    {
      if ( v18[0] && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hObject);
      return updated;
    }
    if ( v12 != -1 )
      *((_DWORD *)this + 34) = v12;
  }
  if ( (a2 & 1) != 0 )
  {
    v11 = LxUtilFsChmod(hObject, *(unsigned int *)a3);
    if ( v11 )
    {
LABEL_13:
      if ( v18[0] )
      {
        if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(hObject);
      }
      return v11;
    }
  }
  if ( (a2 & 0x10) == 0 && (a2 & 0x60) == 0 )
    goto LABEL_55;
  v22 = 0;
  v16 = 1073741822;
  v23 = 1073741822;
  v20 = 0;
  v21 = 1073741822;
  v24[0] = 0;
  if ( (a2 & 0x10) != 0 )
  {
    if ( (a2 & 0x80u) == 0 )
    {
      v23 = 0x3FFFFFFF;
    }
    else
    {
      v22 = *((_QWORD *)a3 + 7);
      v23 = *((_QWORD *)a3 + 8);
    }
  }
  if ( (a2 & 0x20) != 0 )
  {
    if ( (a2 & 0x100) != 0 )
    {
      v20 = *((_QWORD *)a3 + 9);
      v21 = *((_QWORD *)a3 + 10);
    }
    else
    {
      v21 = 0x3FFFFFFF;
    }
  }
  if ( (a2 & 0x40) != 0 )
    v16 = 0x3FFFFFFF;
  v24[1] = v16;
  v17 = LxUtilFsSetTimes(hObject, &v22, &v20, v24);
  if ( v17 )
  {
    if ( v18[0] && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return v17;
  }
  else
  {
LABEL_55:
    if ( v18[0] && (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return 0;
  }
}

```

## disassembly

```asm
0x1800214d0  mov     [rsp-28h+arg_8], rbx
0x1800214d5  push    rbp
0x1800214d6  push    rsi
0x1800214d7  push    rdi
0x1800214d8  push    r14
0x1800214da  push    r15
0x1800214dc  mov     rbp, rsp
0x1800214df  sub     rsp, 70h
0x1800214e3  mov     rax, cs:__security_cookie
0x1800214ea  xor     rax, rsp
0x1800214ed  mov     [rbp+var_10], rax
0x1800214f1  mov     ebx, edx
0x1800214f3  mov     rdi, r8
0x1800214f6  mov     rdx, [rcx+48h]
0x1800214fa  mov     r15, rcx
0x1800214fd  test    byte ptr [rdx+30h], 1
0x180021501  jz      short loc_18002150D
0x180021503  mov     eax, 0FFFFFFE2h
0x180021508  jmp     loc_180021700
0x18002150d  mov     esi, ebx
0x18002150f  and     esi, 8
0x180021512  mov     eax, esi
0x180021514  neg     eax
0x180021516  sbb     ecx, ecx
0x180021518  and     ecx, 2
0x18002151b  add     ecx, 100180h
0x180021521  test    byte ptr [rdx+30h], 4
0x180021525  jz      short loc_180021535
0x180021527  test    dword ptr [rdx+28h], 1000h
0x18002152e  jz      short loc_180021535
0x180021530  mov     r14b, 1
0x180021533  jmp     short loc_180021538
0x180021535  xor     r14b, r14b
0x180021538  mov     r8d, ecx
0x18002153b  lea     rdx, [rbp+var_50]
0x18002153f  or      r8d, 18h
0x180021543  test    r14b, r14b
0x180021546  cmovz   r8d, ecx
0x18002154a  mov     rcx, r15
0x18002154d  call    ?OpenHandle@File@p9fs@@AEBA?AV?$BasicExpected@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@J@util@@K@Z; p9fs::File::OpenHandle(ulong)
0x180021552  cmp     [rbp+var_50], 0
0x180021556  jnz     short loc_180021560
0x180021558  mov     eax, dword ptr [rbp+hObject]
0x18002155b  jmp     loc_180021700
0x180021560  test    esi, esi
0x180021562  jz      short loc_180021599
0x180021564  mov     rdx, [rdi+20h]
0x180021568  mov     rcx, [rbp+hObject]
0x18002156c  call    cs:__imp_LxUtilFsTruncate
0x180021572  mov     esi, eax
0x180021574  test    eax, eax
0x180021576  jz      short loc_180021599
0x180021578  cmp     [rbp+var_50], 0
0x18002157c  jz      short loc_180021592
0x18002157e  mov     rcx, [rbp+hObject]; hObject
0x180021582  lea     rdx, [rcx-1]
0x180021586  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002158a  ja      short loc_180021592
0x18002158c  call    cs:__imp_CloseHandle
0x180021592  mov     eax, esi
0x180021594  jmp     loc_180021700
0x180021599  test    r14b, r14b
0x18002159c  jz      short loc_18002160D
0x18002159e  test    bl, 7
0x1800215a1  jz      short loc_18002160D
0x1800215a3  test    bl, 1
0x1800215a6  jz      short loc_1800215AC
0x1800215a8  mov     esi, [rdi]
0x1800215aa  jmp     short loc_1800215AF
0x1800215ac  or      esi, 0FFFFFFFFh
0x1800215af  test    bl, 2
0x1800215b2  jz      short loc_1800215B9
0x1800215b4  mov     edx, [rdi+4]
0x1800215b7  jmp     short loc_1800215BC
0x1800215b9  or      edx, 0FFFFFFFFh
0x1800215bc  test    bl, 4
0x1800215bf  jz      short loc_1800215C7
0x1800215c1  mov     r8d, [rdi+8]
0x1800215c5  jmp     short loc_1800215CB
0x1800215c7  or      r8d, 0FFFFFFFFh
0x1800215cb  mov     rcx, [rbp+hObject]
0x1800215cf  mov     r9d, esi
0x1800215d2  call    cs:__imp_LxUtilFsUpdateLxAttributes
0x1800215d8  mov     r14d, eax
0x1800215db  test    eax, eax
0x1800215dd  jz      short loc_180021601
0x1800215df  cmp     [rbp+var_50], 0
0x1800215e3  jz      short loc_1800215F9
0x1800215e5  mov     rcx, [rbp+hObject]; hObject
0x1800215e9  lea     rdx, [rcx-1]
0x1800215ed  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800215f1  ja      short loc_1800215F9
0x1800215f3  call    cs:__imp_CloseHandle
0x1800215f9  mov     eax, r14d
0x1800215fc  jmp     loc_180021700
0x180021601  cmp     esi, 0FFFFFFFFh
0x180021604  jz      short loc_18002160D
0x180021606  mov     [r15+88h], esi
0x18002160d  test    bl, 1
0x180021610  jz      short loc_180021628
0x180021612  mov     edx, [rdi]
0x180021614  mov     rcx, [rbp+hObject]
0x180021618  call    cs:__imp_LxUtilFsChmod
0x18002161e  mov     esi, eax
0x180021620  test    eax, eax
0x180021622  jnz     loc_180021578
0x180021628  mov     eax, ebx
0x18002162a  and     eax, 10h
0x18002162d  jnz     short loc_180021638
0x18002162f  test    bl, 60h
0x180021632  jz      loc_1800216E4
0x180021638  mov     [rbp+var_30], 0
0x180021640  mov     ecx, 3FFFFFFEh
0x180021645  mov     [rbp+var_28], rcx
0x180021649  mov     [rbp+var_40], 0
0x180021651  mov     [rbp+var_38], rcx
0x180021655  mov     [rbp+var_20], 0
0x18002165d  lea     edx, [rcx+1]
0x180021660  test    eax, eax
0x180021662  jz      short loc_18002167E
0x180021664  test    bl, bl
0x180021666  jns     short loc_18002167A
0x180021668  mov     rax, [rdi+38h]
0x18002166c  mov     [rbp+var_30], rax
0x180021670  mov     rax, [rdi+40h]
0x180021674  mov     [rbp+var_28], rax
0x180021678  jmp     short loc_18002167E
0x18002167a  mov     [rbp+var_28], rdx
0x18002167e  test    bl, 20h
0x180021681  jz      short loc_18002169F
0x180021683  bt      ebx, 8
0x180021687  jnb     short loc_18002169B
0x180021689  mov     rax, [rdi+48h]
0x18002168d  mov     [rbp+var_40], rax
0x180021691  mov     rax, [rdi+50h]
0x180021695  mov     [rbp+var_38], rax
0x180021699  jmp     short loc_18002169F
0x18002169b  mov     [rbp+var_38], rdx
0x18002169f  test    bl, 40h
0x1800216a2  lea     r9, [rbp+var_20]
0x1800216a6  lea     r8, [rbp+var_40]
0x1800216aa  cmovnz  rcx, rdx
0x1800216ae  lea     rdx, [rbp+var_30]
0x1800216b2  mov     [rbp+var_18], rcx
0x1800216b6  mov     rcx, [rbp+hObject]
0x1800216ba  call    cs:__imp_LxUtilFsSetTimes
0x1800216c0  mov     ebx, eax
0x1800216c2  test    eax, eax
0x1800216c4  jz      short loc_1800216E4
0x1800216c6  cmp     [rbp+var_50], 0
0x1800216ca  jz      short loc_1800216E0
0x1800216cc  mov     rcx, [rbp+hObject]; hObject
0x1800216d0  lea     rdx, [rcx-1]
0x1800216d4  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800216d8  ja      short loc_1800216E0
0x1800216da  call    cs:__imp_CloseHandle
0x1800216e0  mov     eax, ebx
0x1800216e2  jmp     short loc_180021700
0x1800216e4  cmp     [rbp+var_50], 0
0x1800216e8  jz      short loc_1800216FE
0x1800216ea  mov     rcx, [rbp+hObject]; hObject
0x1800216ee  lea     rax, [rcx-1]
0x1800216f2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800216f6  ja      short loc_1800216FE
0x1800216f8  call    cs:__imp_CloseHandle
0x1800216fe  xor     eax, eax
0x180021700  mov     rcx, [rbp+var_10]
0x180021704  xor     rcx, rsp; StackCookie
0x180021707  call    __security_check_cookie
0x18002170c  mov     rbx, [rsp+70h+arg_8]
0x180021714  add     rsp, 70h
0x180021718  pop     r15
0x18002171a  pop     r14
0x18002171c  pop     rdi
0x18002171d  pop     rsi
0x18002171e  pop     rbp
0x18002171f  retn
```
