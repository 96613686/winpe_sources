# CSlideshowSettingsAdapter::IsEqual(ISlideshowSettings *)

- ea: `0x18001be00`
- end: `0x18001bf77`
- name: `?IsEqual@CSlideshowSettingsAdapter@@UEAAHPEAUISlideshowSettings@@@Z`
- size: `375`
- prototype: `__int64 __fastcall(CSlideshowSettingsAdapter *__hidden this, struct ISlideshowSettings *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180005410`
- `0x1800054f8`
- `0x18001be00`
- `0x18006d010`

## import_xrefs

- `SHLWAPI!UrlCompareW` at `0x18001bea2`
- `SHLWAPI!UrlCompareW` at `0x18001bea2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001beb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001beb2`

## pseudocode

```c
__int64 __fastcall CSlideshowSettingsAdapter::IsEqual(CSlideshowSettingsAdapter *this, struct ISlideshowSettings *a2)
{
  unsigned int (__fastcall *v4)(CSlideshowSettingsAdapter *); // rdi
  int v5; // ebx
  unsigned int (__fastcall *v6)(struct ISlideshowSettings *); // rdi
  int v7; // ebx
  const WCHAR *v8; // rax
  __int64 v9; // r9
  WCHAR *v10; // rdi
  unsigned int IsEqual; // ebx
  int (__fastcall **v12)(struct ISlideshowSettings *, GUID *, __int64 *); // rax
  CFileSource *v13; // rdi
  volatile signed __int32 *v14; // rax
  CFileSource *v15; // rsi
  __int64 v17; // [rsp+50h] [rbp+8h] BYREF

  v4 = *(unsigned int (__fastcall **)(CSlideshowSettingsAdapter *))(*(_QWORD *)this + 40LL);
  v5 = (*(__int64 (__fastcall **)(struct ISlideshowSettings *))(*(_QWORD *)a2 + 40LL))(a2);
  if ( v4(this) != v5 )
    return 0;
  v6 = *(unsigned int (__fastcall **)(struct ISlideshowSettings *))(*(_QWORD *)a2 + 48LL);
  v7 = (*(__int64 (__fastcall **)(CSlideshowSettingsAdapter *))(*(_QWORD *)this + 48LL))(this);
  if ( v7 != v6(a2) )
    return 0;
  v8 = (const WCHAR *)(*(__int64 (__fastcall **)(struct ISlideshowSettings *))(*(_QWORD *)a2 + 64LL))(a2);
  v9 = *((_QWORD *)this + 3);
  v10 = (WCHAR *)v8;
  if ( (v8 != 0) != (v9 != 0) )
    return 0;
  if ( v9 )
  {
    IsEqual = UrlCompareW(v8, *((PCWSTR *)this + 3), 0) == 0;
    CoTaskMemFree(v10);
    return IsEqual;
  }
  v12 = *(int (__fastcall ***)(struct ISlideshowSettings *, GUID *, __int64 *))a2;
  v17 = 0;
  if ( (*v12)(a2, &GUID_84d83cf8_dcba_4ea6_b6e5_482d037830ef, &v17) < 0 )
    return 0;
  v13 = (CFileSource *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 24LL))(v17);
  IsEqual = 1;
  v14 = (volatile signed __int32 *)*((_QWORD *)this + 6);
  if ( v14 )
    _InterlockedAdd(v14, 1u);
  v15 = (CFileSource *)*((_QWORD *)this + 6);
  if ( (v13 != 0) == (v15 != 0) )
  {
    if ( v13 )
      IsEqual = (unsigned __int8)CFileSource::IsEqual(v13, *((struct CFileSource **)this + 6));
  }
  else
  {
    IsEqual = 0;
  }
  if ( v15 )
    CFileSource::Release(v15);
  if ( v13 )
    CFileSource::Release(v13);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return IsEqual;
}

```

## disassembly

```asm
0x18001be00  push    rbx
0x18001be02  push    rsi
0x18001be03  push    rdi
0x18001be04  push    r14
0x18001be06  sub     rsp, 28h
0x18001be0a  mov     r8, [rcx]
0x18001be0d  mov     r14, rcx
0x18001be10  mov     rax, [rdx]
0x18001be13  mov     rcx, rdx
0x18001be16  mov     rsi, rdx
0x18001be19  mov     rdi, [r8+28h]
0x18001be1d  mov     rax, [rax+28h]
0x18001be21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be26  mov     ebx, eax
0x18001be28  mov     rcx, r14
0x18001be2b  mov     rax, rdi
0x18001be2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be33  cmp     eax, ebx
0x18001be35  jnz     loc_18001BF69
0x18001be3b  mov     rax, [rsi]
0x18001be3e  mov     rcx, [r14]
0x18001be41  mov     rdi, [rax+30h]
0x18001be45  mov     rax, [rcx+30h]
0x18001be49  mov     rcx, r14
0x18001be4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be51  mov     ebx, eax
0x18001be53  mov     rcx, rsi
0x18001be56  mov     rax, rdi
0x18001be59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be5e  cmp     ebx, eax
0x18001be60  jnz     loc_18001BF69
0x18001be66  mov     rax, [rsi]
0x18001be69  mov     rcx, rsi
0x18001be6c  mov     rax, [rax+40h]
0x18001be70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be75  mov     r9, [r14+18h]
0x18001be79  xor     edx, edx
0x18001be7b  test    r9, r9
0x18001be7e  mov     rdi, rax
0x18001be81  setnz   dl
0x18001be84  xor     ecx, ecx
0x18001be86  test    rax, rax
0x18001be89  setnz   cl
0x18001be8c  cmp     ecx, edx
0x18001be8e  jnz     loc_18001BF69
0x18001be94  test    r9, r9
0x18001be97  jz      short loc_18001BEBD
0x18001be99  xor     r8d, r8d; fIgnoreSlash
0x18001be9c  mov     rdx, r9; psz2
0x18001be9f  mov     rcx, rax; psz1
0x18001bea2  call    cs:__imp_UrlCompareW
0x18001bea8  xor     ebx, ebx
0x18001beaa  mov     rcx, rdi; pv
0x18001bead  test    eax, eax
0x18001beaf  setz    bl
0x18001beb2  call    cs:__imp_CoTaskMemFree
0x18001beb8  jmp     loc_18001BF6B
0x18001bebd  mov     rax, [rsi]
0x18001bec0  lea     r8, [rsp+48h+arg_0]
0x18001bec5  lea     rdx, _GUID_84d83cf8_dcba_4ea6_b6e5_482d037830ef
0x18001becc  mov     [rsp+48h+arg_0], 0
0x18001bed5  mov     rcx, rsi
0x18001bed8  mov     rax, [rax]
0x18001bedb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bee0  test    eax, eax
0x18001bee2  js      loc_18001BF69
0x18001bee8  mov     rcx, [rsp+48h+arg_0]
0x18001beed  mov     rax, [rcx]
0x18001bef0  mov     rax, [rax+18h]
0x18001bef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bef9  mov     rdi, rax
0x18001befc  mov     ebx, 1
0x18001bf01  mov     rax, [r14+30h]
0x18001bf05  test    rax, rax
0x18001bf08  jz      short loc_18001BF0D
0x18001bf0a  lock add [rax], ebx
0x18001bf0d  mov     rsi, [r14+30h]
0x18001bf11  xor     ecx, ecx
0x18001bf13  test    rsi, rsi
0x18001bf16  setnz   cl
0x18001bf19  xor     eax, eax
0x18001bf1b  test    rdi, rdi
0x18001bf1e  setnz   al
0x18001bf21  cmp     eax, ecx
0x18001bf23  jz      short loc_18001BF29
0x18001bf25  xor     ebx, ebx
0x18001bf27  jmp     short loc_18001BF3C
0x18001bf29  test    rdi, rdi
0x18001bf2c  jz      short loc_18001BF3C
0x18001bf2e  mov     rdx, rsi; struct CFileSource *
0x18001bf31  mov     rcx, rdi; this
0x18001bf34  call    ?IsEqual@CFileSource@@QEAA_NPEAV1@@Z; CFileSource::IsEqual(CFileSource *)
0x18001bf39  movzx   ebx, al
0x18001bf3c  test    rsi, rsi
0x18001bf3f  jz      short loc_18001BF49
0x18001bf41  mov     rcx, rsi; this
0x18001bf44  call    ?Release@CFileSource@@QEAAKXZ; CFileSource::Release(void)
0x18001bf49  test    rdi, rdi
0x18001bf4c  jz      short loc_18001BF56
0x18001bf4e  mov     rcx, rdi; this
0x18001bf51  call    ?Release@CFileSource@@QEAAKXZ; CFileSource::Release(void)
0x18001bf56  mov     rcx, [rsp+48h+arg_0]
0x18001bf5b  mov     rax, [rcx]
0x18001bf5e  mov     rax, [rax+10h]
0x18001bf62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf67  jmp     short loc_18001BF6B
0x18001bf69  xor     ebx, ebx
0x18001bf6b  mov     eax, ebx
0x18001bf6d  add     rsp, 28h
0x18001bf71  pop     r14
0x18001bf73  pop     rdi
0x18001bf74  pop     rsi
0x18001bf75  pop     rbx
0x18001bf76  retn
```
