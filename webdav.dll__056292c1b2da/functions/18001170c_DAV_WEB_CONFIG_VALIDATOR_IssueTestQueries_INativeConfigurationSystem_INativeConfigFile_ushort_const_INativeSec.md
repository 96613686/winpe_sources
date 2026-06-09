# DAV_WEB_CONFIG_VALIDATOR::IssueTestQueries(INativeConfigurationSystem *,INativeConfigFile *,ushort const *,INativeSectionException * *)

- ea: `0x18001170c`
- end: `0x1800119be`
- name: `?IssueTestQueries@DAV_WEB_CONFIG_VALIDATOR@@AEAAJPEAVINativeConfigurationSystem@@PEAVINativeConfigFile@@PEBGPEAPEAVINativeSectionException@@@Z`
- size: `690`
- prototype: `__int64 __fastcall(DAV_WEB_CONFIG_VALIDATOR *__hidden this, struct INativeConfigurationSystem *, struct INativeConfigFile *, const unsigned __int16 *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180011cf8`

## callees

- `0x18001170c`
- `0x180022520`
- `0x180023010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180011770`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180011770`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011763`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180011763`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001198f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001198f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001180f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180011827`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18001180f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180011827`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800117f0`
- `iisutil!?SetLen@STRU@@QEAA_NK@Z` at `0x1800117f0`

## pseudocode

```c
__int64 __fastcall DAV_WEB_CONFIG_VALIDATOR::IssueTestQueries(
        DAV_WEB_CONFIG_VALIDATOR *this,
        struct INativeConfigurationSystem *a2,
        struct INativeConfigFile *a3,
        const unsigned __int16 *a4,
        struct INativeSectionException **a5)
{
  unsigned int v5; // esi
  int v9; // ebx
  unsigned int v10; // r15d
  unsigned int v11; // edi
  __int64 v12; // rcx
  __int64 v14; // [rsp+40h] [rbp-51h] BYREF
  unsigned int v15; // [rsp+48h] [rbp-49h] BYREF
  unsigned int v16; // [rsp+4Ch] [rbp-45h] BYREF
  __int64 v17; // [rsp+50h] [rbp-41h] BYREF
  __int64 v18; // [rsp+58h] [rbp-39h] BYREF
  const unsigned __int16 *v19; // [rsp+60h] [rbp-31h] BYREF
  __int64 v20; // [rsp+68h] [rbp-29h] BYREF
  _BYTE v21[32]; // [rsp+70h] [rbp-21h] BYREF
  __int64 v22; // [rsp+90h] [rbp-1h]
  unsigned int v23; // [rsp+A0h] [rbp+Fh]

  v5 = 0;
  v16 = 0;
  v15 = 0;
  v14 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  STRU::STRU((STRU *)v21);
  v9 = STRU::Copy((STRU *)v21, a4);
  if ( v9 >= 0 )
  {
    v10 = v23;
    v9 = (*(__int64 (__fastcall **)(struct INativeConfigFile *, unsigned int *))(*(_QWORD *)a3 + 24LL))(a3, &v16);
    if ( v9 >= 0 )
    {
      v11 = 0;
      if ( v16 )
      {
        while ( 1 )
        {
          v9 = (*(__int64 (__fastcall **)(struct INativeConfigFile *, _QWORD, __int64 *))(*(_QWORD *)a3 + 32LL))(
                 a3,
                 v11,
                 &v14);
          if ( v9 < 0 )
            break;
          v9 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 **))(*(_QWORD *)v14 + 24LL))(v14, &v19);
          if ( v9 < 0 )
            break;
          STRU::SetLen((STRU *)v21, v10);
          if ( v19 )
          {
            if ( *v19 )
            {
              v9 = STRU::Append((STRU *)v21, L"/");
              if ( v9 < 0 )
                break;
              v9 = STRU::Append((STRU *)v21, v19);
              if ( v9 < 0 )
                break;
            }
          }
          v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v14 + 32LL))(v14, &v15);
          if ( v9 < 0 )
            break;
          if ( v15 )
          {
            do
            {
              v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, struct INativeSectionException **))(*(_QWORD *)v14 + 40LL))(
                     v14,
                     v5,
                     &v17,
                     a5);
              if ( v9 < 0 )
                goto LABEL_18;
              v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 24LL))(v17, &v20);
              if ( v9 < 0 )
                goto LABEL_18;
              v9 = (*(__int64 (__fastcall **)(struct INativeConfigurationSystem *, __int64, __int64, __int64 *, struct INativeSectionException **, _QWORD))(*(_QWORD *)a2 + 24LL))(
                     a2,
                     v20,
                     v22,
                     &v18,
                     a5,
                     0);
              if ( v9 < 0 )
                goto LABEL_18;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
              v18 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
              ++v5;
              v17 = 0;
            }
            while ( v5 < v15 );
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          v5 = 0;
          ++v11;
          v12 = 0;
          v14 = 0;
          if ( v11 >= v16 )
            goto LABEL_19;
        }
      }
    }
  }
LABEL_18:
  v12 = v14;
LABEL_19:
  if ( v18 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v12 = v14;
    v18 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v12 = v14;
    v17 = 0;
  }
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v14 = 0;
  }
  STRU::~STRU((STRU *)v21);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001170c  mov     [rsp-8+arg_0], rbx
0x180011711  push    rbp
0x180011712  push    rsi
0x180011713  push    rdi
0x180011714  push    r12
0x180011716  push    r13
0x180011718  push    r14
0x18001171a  push    r15
0x18001171c  lea     rbp, [rsp-1Fh]
0x180011721  sub     rsp, 0B0h
0x180011728  mov     rax, cs:__security_cookie
0x18001172f  xor     rax, rsp
0x180011732  mov     [rbp+4Fh+var_38], rax
0x180011736  mov     r12, [rbp+4Fh+arg_20]
0x18001173a  lea     rcx, [rbp+4Fh+var_70]
0x18001173e  xor     esi, esi
0x180011740  mov     rbx, r9
0x180011743  mov     [rbp+4Fh+var_94], esi
0x180011746  mov     r14, r8
0x180011749  mov     [rbp+4Fh+var_98], esi
0x18001174c  mov     r13, rdx
0x18001174f  mov     [rbp+4Fh+var_A0], rsi
0x180011753  mov     [rbp+4Fh+var_90], rsi
0x180011757  mov     [rbp+4Fh+var_88], rsi
0x18001175b  mov     [rbp+4Fh+var_80], rsi
0x18001175f  mov     [rbp+4Fh+var_78], rsi
0x180011763  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180011769  mov     rdx, rbx
0x18001176c  lea     rcx, [rbp+4Fh+var_70]
0x180011770  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180011776  mov     ebx, eax
0x180011778  test    eax, eax
0x18001177a  js      loc_180011932
0x180011780  mov     rax, [r14]
0x180011783  lea     rdx, [rbp+4Fh+var_94]
0x180011787  mov     r15d, [rbp+4Fh+var_40]
0x18001178b  mov     rcx, r14
0x18001178e  mov     rax, [rax+18h]
0x180011792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011797  mov     ebx, eax
0x180011799  test    eax, eax
0x18001179b  js      loc_180011932
0x1800117a1  mov     edi, esi
0x1800117a3  cmp     [rbp+4Fh+var_94], esi
0x1800117a6  jbe     loc_180011932
0x1800117ac  mov     rax, [r14]
0x1800117af  lea     r8, [rbp+4Fh+var_A0]
0x1800117b3  mov     edx, edi
0x1800117b5  mov     rcx, r14
0x1800117b8  mov     rax, [rax+20h]
0x1800117bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117c1  mov     ebx, eax
0x1800117c3  test    eax, eax
0x1800117c5  js      loc_180011932
0x1800117cb  mov     rcx, [rbp+4Fh+var_A0]
0x1800117cf  lea     rdx, [rbp+4Fh+var_80]
0x1800117d3  mov     rax, [rcx]
0x1800117d6  mov     rax, [rax+18h]
0x1800117da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117df  mov     ebx, eax
0x1800117e1  test    eax, eax
0x1800117e3  js      loc_180011932
0x1800117e9  mov     edx, r15d
0x1800117ec  lea     rcx, [rbp+4Fh+var_70]
0x1800117f0  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x1800117f6  mov     rax, [rbp+4Fh+var_80]
0x1800117fa  test    rax, rax
0x1800117fd  jz      short loc_180011837
0x1800117ff  cmp     [rax], si
0x180011802  jz      short loc_180011837
0x180011804  lea     rdx, asc_180025EA4; "/"
0x18001180b  lea     rcx, [rbp+4Fh+var_70]
0x18001180f  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180011815  mov     ebx, eax
0x180011817  test    eax, eax
0x180011819  js      loc_180011932
0x18001181f  mov     rdx, [rbp+4Fh+var_80]
0x180011823  lea     rcx, [rbp+4Fh+var_70]
0x180011827  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18001182d  mov     ebx, eax
0x18001182f  test    eax, eax
0x180011831  js      loc_180011932
0x180011837  mov     rcx, [rbp+4Fh+var_A0]
0x18001183b  lea     rdx, [rbp+4Fh+var_98]
0x18001183f  mov     rax, [rcx]
0x180011842  mov     rax, [rax+20h]
0x180011846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001184b  mov     ebx, eax
0x18001184d  test    eax, eax
0x18001184f  js      loc_180011932
0x180011855  cmp     [rbp+4Fh+var_98], 0
0x180011859  jbe     loc_18001190B
0x18001185f  mov     rcx, [rbp+4Fh+var_A0]
0x180011863  lea     r8, [rbp+4Fh+var_90]
0x180011867  mov     r9, r12
0x18001186a  mov     edx, esi
0x18001186c  mov     rax, [rcx]
0x18001186f  mov     rax, [rax+28h]
0x180011873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011878  mov     ebx, eax
0x18001187a  test    eax, eax
0x18001187c  js      loc_180011930
0x180011882  mov     rcx, [rbp+4Fh+var_90]
0x180011886  lea     rdx, [rbp+4Fh+var_78]
0x18001188a  mov     rax, [rcx]
0x18001188d  mov     rax, [rax+18h]
0x180011891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011896  mov     ebx, eax
0x180011898  test    eax, eax
0x18001189a  js      loc_180011930
0x1800118a0  mov     rax, [r13+0]
0x1800118a4  lea     r9, [rbp+4Fh+var_88]
0x1800118a8  mov     r8, [rbp+4Fh+var_50]
0x1800118ac  mov     rcx, r13
0x1800118af  mov     rdx, [rbp+4Fh+var_78]
0x1800118b3  mov     [rsp+0E0h+var_B8], 0
0x1800118bc  mov     rax, [rax+18h]
0x1800118c0  mov     [rsp+0E0h+var_C0], r12
0x1800118c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118ca  mov     ebx, eax
0x1800118cc  test    eax, eax
0x1800118ce  js      short loc_180011930
0x1800118d0  mov     rcx, [rbp+4Fh+var_88]
0x1800118d4  mov     rax, [rcx]
0x1800118d7  mov     rax, [rax+10h]
0x1800118db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118e0  mov     rcx, [rbp+4Fh+var_90]
0x1800118e4  mov     [rbp+4Fh+var_88], 0
0x1800118ec  mov     rax, [rcx]
0x1800118ef  mov     rax, [rax+10h]
0x1800118f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118f8  inc     esi
0x1800118fa  mov     [rbp+4Fh+var_90], 0
0x180011902  cmp     esi, [rbp+4Fh+var_98]
0x180011905  jb      loc_18001185F
0x18001190b  mov     rcx, [rbp+4Fh+var_A0]
0x18001190f  mov     rax, [rcx]
0x180011912  mov     rax, [rax+10h]
0x180011916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001191b  xor     esi, esi
0x18001191d  inc     edi
0x18001191f  mov     ecx, esi
0x180011921  mov     [rbp+4Fh+var_A0], rcx
0x180011925  cmp     edi, [rbp+4Fh+var_94]
0x180011928  jb      loc_1800117AC
0x18001192e  jmp     short loc_180011936
0x180011930  xor     esi, esi
0x180011932  mov     rcx, [rbp+4Fh+var_A0]
0x180011936  mov     rdx, [rbp+4Fh+var_88]
0x18001193a  test    rdx, rdx
0x18001193d  jz      short loc_180011956
0x18001193f  mov     rax, [rdx]
0x180011942  mov     rcx, rdx
0x180011945  mov     rax, [rax+10h]
0x180011949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001194e  mov     rcx, [rbp+4Fh+var_A0]
0x180011952  mov     [rbp+4Fh+var_88], rsi
0x180011956  mov     rdx, [rbp+4Fh+var_90]
0x18001195a  test    rdx, rdx
0x18001195d  jz      short loc_180011976
0x18001195f  mov     rax, [rdx]
0x180011962  mov     rcx, rdx
0x180011965  mov     rax, [rax+10h]
0x180011969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001196e  mov     rcx, [rbp+4Fh+var_A0]
0x180011972  mov     [rbp+4Fh+var_90], rsi
0x180011976  test    rcx, rcx
0x180011979  jz      short loc_18001198B
0x18001197b  mov     rax, [rcx]
0x18001197e  mov     rax, [rax+10h]
0x180011982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011987  mov     [rbp+4Fh+var_A0], rsi
0x18001198b  lea     rcx, [rbp+4Fh+var_70]
0x18001198f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180011995  mov     eax, ebx
0x180011997  mov     rcx, [rbp+4Fh+var_38]
0x18001199b  xor     rcx, rsp; StackCookie
0x18001199e  call    __security_check_cookie
0x1800119a3  mov     rbx, [rsp+0E0h+arg_0]
0x1800119ab  add     rsp, 0B0h
0x1800119b2  pop     r15
0x1800119b4  pop     r14
0x1800119b6  pop     r13
0x1800119b8  pop     r12
0x1800119ba  pop     rdi
0x1800119bb  pop     rsi
0x1800119bc  pop     rbp
0x1800119bd  retn
```
