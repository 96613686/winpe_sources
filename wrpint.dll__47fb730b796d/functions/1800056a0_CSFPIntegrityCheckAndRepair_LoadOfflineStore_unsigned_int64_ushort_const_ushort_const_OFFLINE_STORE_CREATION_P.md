# CSFPIntegrityCheckAndRepair::LoadOfflineStore(unsigned __int64,ushort const *,ushort const *,_OFFLINE_STORE_CREATION_PARAMETERS * *)

- ea: `0x1800056a0`
- end: `0x1800058e7`
- name: `?LoadOfflineStore@CSFPIntegrityCheckAndRepair@@EEAAJ_KPEBG1PEAPEAU_OFFLINE_STORE_CREATION_PARAMETERS@@@Z`
- size: `583`
- prototype: `__int64 __fastcall(CSFPIntegrityCheckAndRepair *this, __int64, const unsigned __int16 *, const unsigned __int16 *, struct _OFFLINE_STORE_CREATION_PARAMETERS **)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x1800012f4`
- `0x180001300`
- `0x180001de0`
- `0x1800056a0`
- `0x180006344`
- `0x180006f84`
- `0x1800070f0`
- `0x180010448`
- `0x18001b77a`
- `0x18001b7b0`
- `0x18001c010`

## string_xrefs

- `0x1800056d2`: `\System32\config\`

## pseudocode

```c
__int64 __fastcall CSFPIntegrityCheckAndRepair::LoadOfflineStore(
        CSFPIntegrityCheckAndRepair *this,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct _OFFLINE_STORE_CREATION_PARAMETERS **a5)
{
  struct _OFFLINE_STORE_CREATION_PARAMETERS *v5; // rsi
  __int64 v8; // r15
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // r13
  int OfflineRegistryKey; // ebx
  __int64 v13; // r14
  __int64 v14; // rcx
  __int64 v15; // rcx
  char *v16; // rax
  __int64 i; // r14
  struct IMalloc *v18; // r8
  CSFPIntegrityCheckAndRepair *v19; // rcx
  const unsigned __int16 *v21; // r8
  __int64 v22; // [rsp+30h] [rbp-30h] BYREF
  const unsigned __int16 *v23; // [rsp+38h] [rbp-28h]
  struct _OFFLINE_STORE_CREATION_PARAMETERS **v24; // [rsp+40h] [rbp-20h]
  __int64 v25; // [rsp+48h] [rbp-18h] BYREF
  CSFPIntegrityCheckAndRepair *v26; // [rsp+50h] [rbp-10h] BYREF

  v5 = 0;
  v23 = a3;
  v24 = a5;
  v22 = 0;
  v25 = 0;
  v26 = 0;
  v8 = 0;
  v9 = SczAllocConcat2Sz(&v22, a4, L"\\System32\\config\\");
  v11 = v22;
  OfflineRegistryKey = v9;
  if ( v9 >= 0 )
  {
    v13 = 0;
    while ( 1 )
    {
      OfflineRegistryKey = LoadOfflineRegistryKey(
                             v10,
                             v11,
                             (&REGISTRY_HIVE_NAMES)[v13],
                             (char *)this + 16 * v13 + 8 * v13 + 16);
      if ( OfflineRegistryKey < 0 )
        break;
      v13 = (unsigned int)(v13 + 1);
      if ( (unsigned int)v13 >= 6 )
      {
        OfflineRegistryKey = (*(__int64 (__fastcall **)(CSFPIntegrityCheckAndRepair *, const unsigned __int16 *, __int64 *))(*(_QWORD *)this + 56LL))(
                               this,
                               a4,
                               &v25);
        if ( OfflineRegistryKey >= 0 )
        {
          OfflineRegistryKey = LoadOfflineRegistryKey(v14, v25, L"ntuser.dat", (char *)this + 160);
          if ( OfflineRegistryKey >= 0 )
          {
            OfflineRegistryKey = (*(__int64 (__fastcall **)(CSFPIntegrityCheckAndRepair *, const unsigned __int16 *, CSFPIntegrityCheckAndRepair **))(*(_QWORD *)this + 64LL))(
                                   this,
                                   a4,
                                   &v26);
            if ( OfflineRegistryKey >= 0 )
            {
              OfflineRegistryKey = LoadOfflineRegistryKey(v15, v26, L"schema.dat", (char *)this + 184);
              if ( OfflineRegistryKey >= 0 )
              {
                v8 = qword_18002B8B0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_18002B8B0 + 8LL))(qword_18002B8B0);
                v16 = (char *)operator new(0x70u);
                v5 = (struct _OFFLINE_STORE_CREATION_PARAMETERS *)v16;
                if ( !v16 )
                {
                  OfflineRegistryKey = -2147024882;
                  break;
                }
                memset_0(v16 + 8, 0, 0x68u);
                v21 = v23;
                *(_QWORD *)v5 = 112;
                OfflineRegistryKey = (*(__int64 (__fastcall **)(CSFPIntegrityCheckAndRepair *, struct _OFFLINE_STORE_CREATION_PARAMETERS *, const unsigned __int16 *, const unsigned __int16 *, __int64))(*(_QWORD *)this + 72LL))(
                                       this,
                                       v5,
                                       v21,
                                       a4,
                                       v8);
                if ( OfflineRegistryKey >= 0 )
                {
                  *v24 = v5;
                  v5 = 0;
                  OfflineRegistryKey = 0;
                  goto LABEL_14;
                }
              }
            }
          }
        }
        break;
      }
    }
  }
  for ( i = 0; i != 6; ++i )
    UnloadOfflineRegistryKey((char *)this + 16 * i + 8 * i + 16);
  UnloadOfflineRegistryKey((char *)this + 160);
  UnloadOfflineRegistryKey((char *)this + 184);
LABEL_14:
  if ( v25 )
    operator delete((void *)(v25 - 8));
  v19 = v26;
  if ( v26 )
    operator delete((char *)v26 - 8);
  if ( v11 )
    operator delete((void *)(v11 - 8));
  if ( v5 )
  {
    CSFPIntegrityCheckAndRepair::ReleaseOfflineStoreCreationParametersInternals(v19, v5, v18);
    operator delete(v5);
  }
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)OfflineRegistryKey;
}

```

## disassembly

```asm
0x1800056a0  mov     [rsp-38h+arg_8], rbx
0x1800056a5  push    rbp
0x1800056a6  push    rsi
0x1800056a7  push    rdi
0x1800056a8  push    r12
0x1800056aa  push    r13
0x1800056ac  push    r14
0x1800056ae  push    r15
0x1800056b0  mov     rbp, rsp
0x1800056b3  sub     rsp, 60h
0x1800056b7  mov     rax, cs:__security_cookie
0x1800056be  xor     rax, rsp
0x1800056c1  mov     [rbp+var_8], rax
0x1800056c5  mov     rax, [rbp+arg_20]
0x1800056c9  xor     esi, esi
0x1800056cb  mov     [rbp+var_28], r8
0x1800056cf  mov     rdi, rcx
0x1800056d2  lea     r8, aSystem32Config; "\\System32\\config\\"
0x1800056d9  mov     [rbp+var_20], rax
0x1800056dd  lea     rcx, [rbp+var_30]
0x1800056e1  mov     [rbp+var_30], rsi
0x1800056e5  mov     rdx, r9
0x1800056e8  mov     [rbp+var_18], rsi
0x1800056ec  mov     [rbp+var_10], rsi
0x1800056f0  mov     r12, r9
0x1800056f3  xor     r15d, r15d
0x1800056f6  call    SczAllocConcat2Sz
0x1800056fb  mov     r13, [rbp+var_30]
0x1800056ff  mov     ebx, eax
0x180005701  test    eax, eax
0x180005703  js      loc_1800057E7
0x180005709  xor     r14d, r14d
0x18000570c  lea     rax, [r14+1]
0x180005710  mov     rdx, r13
0x180005713  lea     rax, [r14+rax*2]
0x180005717  lea     r9, [rdi+rax*8]
0x18000571b  lea     rax, ?REGISTRY_HIVE_NAMES@@3PAPEBGA; ushort const * near * REGISTRY_HIVE_NAMES
0x180005722  mov     r8, [rax+r14*8]
0x180005726  call    LoadOfflineRegistryKey
0x18000572b  mov     ebx, eax
0x18000572d  test    eax, eax
0x18000572f  js      loc_1800057E7
0x180005735  inc     r14d
0x180005738  cmp     r14d, 6
0x18000573c  jb      short loc_18000570C
0x18000573e  mov     rax, [rdi]
0x180005741  lea     r8, [rbp+var_18]
0x180005745  mov     rdx, r12
0x180005748  mov     rcx, rdi
0x18000574b  mov     rax, [rax+38h]
0x18000574f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005754  mov     ebx, eax
0x180005756  test    eax, eax
0x180005758  js      loc_1800057E7
0x18000575e  mov     rdx, [rbp+var_18]
0x180005762  lea     r9, [rdi+0A0h]
0x180005769  lea     r8, aNtuserDat; "ntuser.dat"
0x180005770  call    LoadOfflineRegistryKey
0x180005775  mov     ebx, eax
0x180005777  test    eax, eax
0x180005779  js      short loc_1800057E7
0x18000577b  mov     rax, [rdi]
0x18000577e  lea     r8, [rbp+var_10]
0x180005782  mov     rdx, r12
0x180005785  mov     rcx, rdi
0x180005788  mov     rax, [rax+40h]
0x18000578c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005791  mov     ebx, eax
0x180005793  test    eax, eax
0x180005795  js      short loc_1800057E7
0x180005797  mov     rdx, [rbp+var_10]
0x18000579b  lea     r9, [rdi+0B8h]
0x1800057a2  lea     r8, aSchemaDat; "schema.dat"
0x1800057a9  call    LoadOfflineRegistryKey
0x1800057ae  mov     ebx, eax
0x1800057b0  test    eax, eax
0x1800057b2  js      short loc_1800057E7
0x1800057b4  mov     r15, cs:qword_18002B8B0
0x1800057bb  mov     rcx, r15
0x1800057be  mov     rax, [r15]
0x1800057c1  mov     rax, [rax+8]
0x1800057c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057ca  mov     ebx, 70h ; 'p'
0x1800057cf  mov     ecx, ebx; Size
0x1800057d1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800057d6  mov     rsi, rax
0x1800057d9  test    rax, rax
0x1800057dc  jnz     loc_18000589D
0x1800057e2  mov     ebx, 8007000Eh
0x1800057e7  xor     r14d, r14d
0x1800057ea  lea     rax, [r14+1]
0x1800057ee  lea     rax, [r14+rax*2]
0x1800057f2  lea     rcx, [rdi+rax*8]
0x1800057f6  call    UnloadOfflineRegistryKey
0x1800057fb  inc     r14
0x1800057fe  cmp     r14, 6
0x180005802  jnz     short loc_1800057EA
0x180005804  lea     rcx, [rdi+0A0h]
0x18000580b  call    UnloadOfflineRegistryKey
0x180005810  lea     rcx, [rdi+0B8h]
0x180005817  call    UnloadOfflineRegistryKey
0x18000581c  mov     rcx, [rbp+var_18]
0x180005820  test    rcx, rcx
0x180005823  jz      short loc_18000582E
0x180005825  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x180005829  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000582e  mov     rcx, [rbp+var_10]
0x180005832  test    rcx, rcx
0x180005835  jz      short loc_180005840
0x180005837  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x18000583b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005840  test    r13, r13
0x180005843  jz      short loc_18000584E
0x180005845  lea     rcx, [r13-8]; Block
0x180005849  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000584e  test    rsi, rsi
0x180005851  jz      short loc_180005863
0x180005853  mov     rdx, rsi; struct _OFFLINE_STORE_CREATION_PARAMETERS *
0x180005856  call    ?ReleaseOfflineStoreCreationParametersInternals@CSFPIntegrityCheckAndRepair@@AEAAJPEAU_OFFLINE_STORE_CREATION_PARAMETERS@@PEAUIMalloc@@@Z; CSFPIntegrityCheckAndRepair::ReleaseOfflineStoreCreationParametersInternals(_OFFLINE_STORE_CREATION_PARAMETERS *,IMalloc *)
0x18000585b  mov     rcx, rsi; Block
0x18000585e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005863  test    r15, r15
0x180005866  jz      short loc_180005877
0x180005868  mov     rax, [r15]
0x18000586b  mov     rcx, r15
0x18000586e  mov     rax, [rax+10h]
0x180005872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005877  mov     eax, ebx
0x180005879  mov     rcx, [rbp+var_8]
0x18000587d  xor     rcx, rsp; StackCookie
0x180005880  call    __security_check_cookie
0x180005885  mov     rbx, [rsp+60h+arg_8]
0x18000588d  add     rsp, 60h
0x180005891  pop     r15
0x180005893  pop     r14
0x180005895  pop     r13
0x180005897  pop     r12
0x180005899  pop     rdi
0x18000589a  pop     rsi
0x18000589b  pop     rbp
0x18000589c  retn
0x18000589d  xor     edx, edx; Val
0x18000589f  lea     rcx, [rax+8]; void *
0x1800058a3  lea     r8d, [rdx+68h]; Size
0x1800058a7  call    memset_0
0x1800058ac  mov     r8, [rbp+var_28]
0x1800058b0  mov     r9, r12
0x1800058b3  mov     [rsi], rbx
0x1800058b6  mov     rdx, rsi
0x1800058b9  mov     rax, [rdi]
0x1800058bc  mov     rcx, rdi
0x1800058bf  mov     [rsp+60h+var_40], r15
0x1800058c4  mov     rax, [rax+48h]
0x1800058c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058cd  mov     ebx, eax
0x1800058cf  test    eax, eax
0x1800058d1  js      loc_1800057E7
0x1800058d7  mov     rax, [rbp+var_20]
0x1800058db  mov     [rax], rsi
0x1800058de  xor     esi, esi
0x1800058e0  xor     ebx, ebx
0x1800058e2  jmp     loc_18000581C
```
