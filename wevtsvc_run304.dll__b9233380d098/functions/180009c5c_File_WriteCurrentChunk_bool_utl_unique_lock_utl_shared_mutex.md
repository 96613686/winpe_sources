# File::WriteCurrentChunk(bool,utl::unique_lock<utl::shared_mutex> &)

- ea: `0x180009c5c`
- end: `0x180009fa2`
- name: `?WriteCurrentChunk@File@@AEAAK_NAEAV?$unique_lock@Vshared_mutex@utl@@@utl@@@Z`
- size: `838`
- prototype: ``
- caller_count: `7`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180008340`
- `0x18000b8f4`
- `0x18000bc38`
- `0x180040b48`
- `0x180040f2c`
- `0x180047a0c`
- `0x1800b27a8`

## callees

- `0x180009c5c`
- `0x180009fa8`
- `0x18000a108`
- `0x18000a180`
- `0x18000a268`
- `0x18000bc0c`
- `0x18001c310`
- `0x180048ffc`
- `0x180092008`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009dab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009dab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009d66`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009d66`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009d79`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009d79`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180009e2b`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180009e2b`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180009d6f`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180009d6f`

## pseudocode

```c
__int64 __fastcall File::WriteCurrentChunk(__int64 a1, char a2, __int64 a3)
{
  unsigned int *v6; // rbx
  __int64 v7; // rax
  unsigned int v8; // r12d
  unsigned int v9; // r14d
  void *v10; // r15
  unsigned int v11; // r8d
  void *v12; // rdx
  FileView *v13; // rcx
  unsigned int v14; // ebp
  unsigned int v15; // r9d
  struct _TP_TIMER *v16; // rcx
  __int64 v18; // rax
  void *v19; // rdx
  unsigned int v20; // eax
  unsigned int v21; // ebx
  __int64 v22; // rcx
  _QWORD v23[2]; // [rsp+20h] [rbp-78h] BYREF
  __int64 v24; // [rsp+30h] [rbp-68h]
  __int64 v25; // [rsp+38h] [rbp-60h]
  int v26; // [rsp+40h] [rbp-58h]
  char v27; // [rsp+49h] [rbp-4Fh]

  if ( *(_BYTE *)(a1 + 831) )
  {
    v18 = *(_QWORD *)(a1 + 144);
    v24 = v18;
    v26 = 128;
    v27 = 0;
    v23[0] = v18;
    if ( v18 )
      v25 = v18 + 128;
    else
      v25 = 0;
    v19 = *(void **)(a1 + 672);
    v23[1] = 0;
    v20 = FileView::ActualWrite((FileView *)v23, v19, 0, 0x80u);
    v21 = v20;
    if ( v20 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v20);
      }
      FileView::~FileView((FileView *)v23);
      return v21;
    }
    FlushFileBuffers(*(HANDLE *)(a1 + 672));
    *(_BYTE *)(a1 + 831) = 0;
    v22 = *(_QWORD *)(a1 + 144);
    *(_QWORD *)(a1 + 144) = 0;
    if ( v22 )
      utl::_RefCountVtable<utl::_RefCountStored<PublisherManifestResource,utl::allocator<int>,0>,0>::_FreeRefCount(
        v22,
        128);
    if ( v27 )
      utl::_RefCountVtable<utl::_RefCountStored<PublisherManifestResource,utl::allocator<int>,0>,0>::_FreeRefCount(
        v24,
        1);
  }
  if ( !*(_BYTE *)(a1 + 827) )
  {
    *(_DWORD *)(a1 + 812) = 0;
    return 0;
  }
  if ( !*(_QWORD *)(a1 + 176) )
    return 0;
  if ( !(unsigned __int8)AreAnyRestrictionsEnabled(1024) || (*(_BYTE *)(a1 + 825) & 8) != 0 )
  {
    WriteFileView::UpdateBothCRCValues((WriteFileView *)(a1 + 152));
    v6 = (unsigned int *)(a1 + 160);
    v7 = a1 + 160;
  }
  else
  {
    v6 = (unsigned int *)(a1 + 160);
    *(_DWORD *)(*(_QWORD *)(a1 + 160) + 52LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 160) + 124LL) = 0;
    *(_DWORD *)(*(_QWORD *)(a1 + 160) + 120LL) |= 4u;
    v7 = a1 + 160;
  }
  *(_BYTE *)(a1 + 838) = 1;
  if ( a2 )
  {
    if ( *(_BYTE *)(a1 + 829) )
      utl::unique_lock<utl::shared_mutex>::unlock(a3);
    v14 = FileView::ActualWrite((FileView *)v6, *(void **)(a1 + 672), 0, v6[8]);
    if ( *(_BYTE *)(a1 + 829) )
      utl::unique_lock<utl::shared_mutex>::lock(a3);
    if ( !v14 )
    {
      *(_DWORD *)(a1 + 812) = 0;
      *(_BYTE *)(a1 + 827) = 0;
    }
    goto LABEL_17;
  }
  v8 = *(_DWORD *)(a1 + 812);
  v9 = *(_DWORD *)(*(_QWORD *)v7 + 48LL);
  if ( *(_BYTE *)(a1 + 829) )
    utl::unique_lock<utl::shared_mutex>::unlock(a3);
  v10 = *(void **)(a1 + 672);
  v11 = 0;
  v12 = v10;
  v13 = (FileView *)v6;
  if ( !v8 )
  {
    v15 = v9;
    goto LABEL_12;
  }
  v14 = FileView::ActualWrite((FileView *)v6, v10, 0, 0x200u);
  if ( !v14 )
  {
    v11 = v8;
    v15 = v9 - v8;
    v12 = v10;
    v13 = (FileView *)v6;
LABEL_12:
    v14 = FileView::ActualWrite(v13, v12, v11, v15);
  }
  if ( *(_BYTE *)(a1 + 829) )
    utl::unique_lock<utl::shared_mutex>::lock(a3);
  if ( !v14 )
    *(_DWORD *)(a1 + 812) = v9;
LABEL_17:
  *(_BYTE *)(a1 + 838) = 0;
  AcquireSRWLockExclusive((PSRWLOCK)(a1 + 752));
  WakeAllConditionVariable((PCONDITION_VARIABLE)(a1 + 744));
  ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 752));
  if ( !v14 )
  {
    v16 = *(struct _TP_TIMER **)(a1 + 656);
    if ( v16 )
    {
      if ( *(_BYTE *)(a1 + 837) )
      {
        *(_BYTE *)(a1 + 837) = 0;
        SetThreadpoolTimer(v16, 0, 0, 0);
      }
    }
    *(_BYTE *)(a1 + 826) = 0;
    return 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_d3d936efbc913e3641017ad303784371_Traceguids, v14);
  }
  return v14;
}

```

## disassembly

```asm
0x180009c5c  push    rbx
0x180009c5e  push    rbp
0x180009c5f  push    rsi
0x180009c60  push    rdi
0x180009c61  push    r12
0x180009c63  push    r13
0x180009c65  push    r14
0x180009c67  push    r15
0x180009c69  sub     rsp, 58h
0x180009c6d  xor     r13d, r13d
0x180009c70  mov     rdi, r8
0x180009c73  mov     bpl, dl
0x180009c76  mov     rsi, rcx
0x180009c79  cmp     [rcx+33Fh], r13b
0x180009c80  jnz     loc_180009DCB
0x180009c86  cmp     [rsi+33Bh], r13b
0x180009c8d  jz      loc_180009F24
0x180009c93  lea     rbx, [rsi+98h]
0x180009c9a  cmp     [rbx+18h], r13
0x180009c9e  jz      loc_180009DB8
0x180009ca4  mov     ecx, 400h
0x180009ca9  call    ?AreAnyRestrictionsEnabled@@YA_NW4FeatureRestrictions@@@Z; AreAnyRestrictionsEnabled(FeatureRestrictions)
0x180009cae  test    al, al
0x180009cb0  jnz     loc_180009F30
0x180009cb6  mov     rcx, rbx; this
0x180009cb9  call    ?UpdateBothCRCValues@WriteFileView@@QEAAXXZ; WriteFileView::UpdateBothCRCValues(void)
0x180009cbe  add     rbx, 8
0x180009cc2  lea     rax, [rsi+0A0h]
0x180009cc9  mov     byte ptr [rsi+346h], 1
0x180009cd0  test    bpl, bpl
0x180009cd3  jnz     loc_180009E72
0x180009cd9  mov     rax, [rax]
0x180009cdc  mov     r12d, [rsi+32Ch]
0x180009ce3  mov     r14d, [rax+30h]
0x180009ce7  cmp     [rsi+33Dh], r13b
0x180009cee  jz      short loc_180009CF8
0x180009cf0  mov     rcx, rdi
0x180009cf3  call    ?unlock@?$unique_lock@Vshared_mutex@utl@@@utl@@QEAAXXZ; utl::unique_lock<utl::shared_mutex>::unlock(void)
0x180009cf8  mov     r15, [rsi+2A0h]
0x180009cff  xor     r8d, r8d; unsigned int
0x180009d02  mov     rdx, r15; void *
0x180009d05  mov     rcx, rbx; this
0x180009d08  test    r12d, r12d
0x180009d0b  jz      loc_180009EC7
0x180009d11  mov     r9d, 200h; unsigned int
0x180009d17  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x180009d1c  mov     ebp, eax
0x180009d1e  test    eax, eax
0x180009d20  jnz     short loc_180009D38
0x180009d22  mov     r9d, r14d
0x180009d25  mov     r8d, r12d; unsigned int
0x180009d28  sub     r9d, r12d; unsigned int
0x180009d2b  mov     rdx, r15; void *
0x180009d2e  mov     rcx, rbx; this
0x180009d31  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x180009d36  mov     ebp, eax
0x180009d38  cmp     [rsi+33Dh], r13b
0x180009d3f  jz      short loc_180009D49
0x180009d41  mov     rcx, rdi
0x180009d44  call    ?lock@?$unique_lock@Vshared_mutex@utl@@@utl@@QEAAXXZ; utl::unique_lock<utl::shared_mutex>::lock(void)
0x180009d49  test    ebp, ebp
0x180009d4b  jnz     short loc_180009D54
0x180009d4d  mov     [rsi+32Ch], r14d
0x180009d54  lea     rbx, [rsi+2E8h]
0x180009d5b  mov     [rsi+346h], r13b
0x180009d62  lea     rcx, [rbx+8]; SRWLock
0x180009d66  call    cs:__imp_AcquireSRWLockExclusive
0x180009d6c  mov     rcx, rbx; ConditionVariable
0x180009d6f  call    cs:__imp_WakeAllConditionVariable
0x180009d75  lea     rcx, [rbx+8]; SRWLock
0x180009d79  call    cs:__imp_ReleaseSRWLockExclusive
0x180009d7f  test    ebp, ebp
0x180009d81  jnz     loc_180009F61
0x180009d87  mov     rcx, [rsi+290h]; pti
0x180009d8e  test    rcx, rcx
0x180009d91  jz      short loc_180009DB1
0x180009d93  cmp     [rsi+345h], r13b
0x180009d9a  jz      short loc_180009DB1
0x180009d9c  xor     r9d, r9d; msWindowLength
0x180009d9f  mov     [rsi+345h], r13b
0x180009da6  xor     r8d, r8d; msPeriod
0x180009da9  xor     edx, edx; pftDueTime
0x180009dab  call    cs:__imp_SetThreadpoolTimer
0x180009db1  mov     [rsi+33Ah], r13b
0x180009db8  xor     eax, eax
0x180009dba  add     rsp, 58h
0x180009dbe  pop     r15
0x180009dc0  pop     r14
0x180009dc2  pop     r13
0x180009dc4  pop     r12
0x180009dc6  pop     rdi
0x180009dc7  pop     rsi
0x180009dc8  pop     rbp
0x180009dc9  pop     rbx
0x180009dca  retn
0x180009dcb  mov     rax, [rcx+90h]
0x180009dd2  mov     r14d, 80h
0x180009dd8  mov     [rsp+98h+var_68], rax
0x180009ddd  mov     [rsp+98h+var_58], r14d
0x180009de2  mov     [rsp+98h+var_4F], r13b
0x180009de7  mov     [rsp+98h+var_78], rax
0x180009dec  test    rax, rax
0x180009def  jz      loc_180009ECF
0x180009df5  sub     rax, 0FFFFFFFFFFFFFF80h
0x180009df9  mov     [rsp+98h+var_60], rax
0x180009dfe  mov     rdx, [rcx+2A0h]; void *
0x180009e05  mov     r9d, r14d; unsigned int
0x180009e08  lea     rcx, [rsp+98h+var_78]; this
0x180009e0d  mov     [rsp+98h+var_70], r13
0x180009e12  xor     r8d, r8d; unsigned int
0x180009e15  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x180009e1a  mov     ebx, eax
0x180009e1c  test    eax, eax
0x180009e1e  jnz     loc_180009ED9
0x180009e24  mov     rcx, [rsi+2A0h]; hFile
0x180009e2b  call    cs:__imp_FlushFileBuffers
0x180009e31  mov     [rsi+33Fh], r13b
0x180009e38  mov     rcx, [rsi+90h]
0x180009e3f  mov     [rsi+90h], r13
0x180009e46  test    rcx, rcx
0x180009e49  jz      short loc_180009E53
0x180009e4b  mov     rdx, r14
0x180009e4e  call    ?_FreeRefCount@?$_RefCountVtable@V?$_RefCountStored@VPublisherManifestResource@@V?$allocator@H@utl@@$0A@@utl@@$0A@@utl@@UEAAXXZ; utl::_RefCountVtable<utl::_RefCountStored<PublisherManifestResource,utl::allocator<int>,0>,0>::_FreeRefCount(void)
0x180009e53  cmp     [rsp+98h+var_4F], r13b
0x180009e58  jz      loc_180009C86
0x180009e5e  mov     rcx, [rsp+98h+var_68]
0x180009e63  mov     edx, 1
0x180009e68  call    ?_FreeRefCount@?$_RefCountVtable@V?$_RefCountStored@VPublisherManifestResource@@V?$allocator@H@utl@@$0A@@utl@@$0A@@utl@@UEAAXXZ; utl::_RefCountVtable<utl::_RefCountStored<PublisherManifestResource,utl::allocator<int>,0>,0>::_FreeRefCount(void)
0x180009e6d  jmp     loc_180009C86
0x180009e72  cmp     [rsi+33Dh], r13b
0x180009e79  jz      short loc_180009E83
0x180009e7b  mov     rcx, rdi
0x180009e7e  call    ?unlock@?$unique_lock@Vshared_mutex@utl@@@utl@@QEAAXXZ; utl::unique_lock<utl::shared_mutex>::unlock(void)
0x180009e83  mov     r9d, [rbx+20h]; unsigned int
0x180009e87  xor     r8d, r8d; unsigned int
0x180009e8a  mov     rdx, [rsi+2A0h]; void *
0x180009e91  mov     rcx, rbx; this
0x180009e94  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x180009e99  mov     ebp, eax
0x180009e9b  cmp     [rsi+33Dh], r13b
0x180009ea2  jz      short loc_180009EAC
0x180009ea4  mov     rcx, rdi
0x180009ea7  call    ?lock@?$unique_lock@Vshared_mutex@utl@@@utl@@QEAAXXZ; utl::unique_lock<utl::shared_mutex>::lock(void)
0x180009eac  test    ebp, ebp
0x180009eae  jnz     loc_180009D54
0x180009eb4  mov     [rsi+32Ch], r13d
0x180009ebb  mov     [rsi+33Bh], r13b
0x180009ec2  jmp     loc_180009D54
0x180009ec7  mov     r9d, r14d
0x180009eca  jmp     loc_180009D31
0x180009ecf  mov     [rsp+98h+var_60], r13
0x180009ed4  jmp     loc_180009DFE
0x180009ed9  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ee0  lea     rdx, WPP_GLOBAL_Control
0x180009ee7  cmp     rcx, rdx
0x180009eea  jz      short loc_180009F13
0x180009eec  test    dword ptr [rcx+1Ch], 8000h
0x180009ef3  jz      short loc_180009F13
0x180009ef5  cmp     byte ptr [rcx+19h], 2
0x180009ef9  jb      short loc_180009F13
0x180009efb  mov     rcx, [rcx+10h]
0x180009eff  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x180009f06  mov     edx, 2Ah ; '*'
0x180009f0b  mov     r9d, ebx
0x180009f0e  call    WPP_SF_d
0x180009f13  lea     rcx, [rsp+98h+var_78]; this
0x180009f18  call    ??1FileView@@QEAA@XZ; FileView::~FileView(void)
0x180009f1d  mov     eax, ebx
0x180009f1f  jmp     loc_180009DBA
0x180009f24  mov     [rsi+32Ch], r13d
0x180009f2b  jmp     loc_180009DB8
0x180009f30  test    byte ptr [rsi+339h], 8
0x180009f37  jnz     loc_180009CB6
0x180009f3d  lea     rbx, [rsi+0A0h]
0x180009f44  mov     rax, [rbx]
0x180009f47  mov     [rax+34h], r13d
0x180009f4b  mov     rax, [rbx]
0x180009f4e  mov     [rax+7Ch], r13d
0x180009f52  mov     rax, [rbx]
0x180009f55  or      dword ptr [rax+78h], 4
0x180009f59  mov     rax, rbx
0x180009f5c  jmp     loc_180009CC9
0x180009f61  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f68  lea     rdx, WPP_GLOBAL_Control
0x180009f6f  cmp     rcx, rdx
0x180009f72  jz      short loc_180009F9B
0x180009f74  test    dword ptr [rcx+1Ch], 8000h
0x180009f7b  jz      short loc_180009F9B
0x180009f7d  cmp     byte ptr [rcx+19h], 2
0x180009f81  jb      short loc_180009F9B
0x180009f83  mov     rcx, [rcx+10h]
0x180009f87  lea     r8, WPP_d3d936efbc913e3641017ad303784371_Traceguids
0x180009f8e  mov     edx, 2Bh ; '+'
0x180009f93  mov     r9d, ebp
0x180009f96  call    WPP_SF_d
0x180009f9b  mov     eax, ebp
0x180009f9d  jmp     loc_180009DBA
```
