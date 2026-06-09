# CSimpleAppList::_OnChange(long,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x18025f6fc`
- end: `0x18025f8fd`
- name: `?_OnChange@CSimpleAppList@@AEAAXJPEBU_ITEMIDLIST_ABSOLUTE@@0@Z`
- size: `513`
- prototype: `void(CSimpleAppList *__hidden this, int, const struct _ITEMIDLIST_ABSOLUTE *, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18025ee58`

## callees

- `0x18000b7e8`
- `0x180011884`
- `0x1801aef88`
- `0x18025ec70`
- `0x18025f6fc`
- `0x18037470c`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18025f7ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18025f8cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18025f7ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18025f8cc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18025f7ca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18025f7ca`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18025f8c2`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x18025f8c2`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x18025f792`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemWithParent` at `0x18025f792`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x18025f89a`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x18025f89a`
- `api-ms-win-shell-namespace-l1-1-0!ILFindChild` at `0x18025f73c`
- `api-ms-win-shell-namespace-l1-1-0!ILFindChild` at `0x18025f73c`

## pseudocode

```c
void __fastcall CSimpleAppList::_OnChange(
        CSimpleAppList *this,
        int a2,
        const ITEMIDLIST *a3,
        const struct _ITEMIDLIST_ABSOLUTE *a4)
{
  LPITEMIDLIST v6; // rax
  const ITEMIDLIST *v7; // r14
  _WORD *v8; // rax
  void **ppvItem; // rax
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, const PROPERTYKEY *, LPVOID *); // rbx
  int v12; // edi
  LPVOID v13; // r15
  unsigned int i; // ebx
  __int64 v15; // rdx
  ITEMIDLIST *v16; // rbx
  __int64 v17; // [rsp+30h] [rbp-20h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-18h] BYREF
  __int64 v19; // [rsp+40h] [rbp-10h] BYREF
  int v20; // [rsp+88h] [rbp+38h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp+48h] BYREF

  ppv = a4;
  if ( a2 == 2 || a2 == 4 )
  {
    v6 = ILFindChild(*(LPITEMIDLIST *)(*((_QWORD *)this + 25) + 24LL), a3);
    v7 = v6;
    if ( v6 )
    {
      if ( !v6->mkid.cb || (v8 = (USHORT *)((char *)&v6->mkid.cb + v6->mkid.cb)) == 0 || !*v8 )
      {
        v17 = 0;
        ppvItem = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(&v17);
        if ( SHCreateItemWithParent(
               *(LPCITEMIDLIST *)(*((_QWORD *)this + 25) + 24LL),
               0,
               v7,
               &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
               ppvItem) < 0 )
        {
LABEL_23:
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v17);
          return;
        }
        ppv = 0;
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
        if ( CoCreateInstance(&CLSID_BackgroundTaskCapability, 0, 1u, &GUID_d54e68c2_54cd_48b3_ad9a_3f4a4503ba80, &ppv) < 0 )
        {
LABEL_22:
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppv);
          goto LABEL_23;
        }
        v10 = v17;
        pv = 0;
        v11 = *(int (__fastcall **)(__int64, const PROPERTYKEY *, LPVOID *))(*(_QWORD *)v17 + 136LL);
        CoTaskMemFree(0);
        if ( v11(v10, &PKEY_AppUserModel_ID, &pv) >= 0 )
        {
          v20 = 0;
          if ( a2 == 4 )
          {
            v12 = 1;
            goto LABEL_14;
          }
          if ( (int)IsAppLockScreenCapable(v17, ppv, *(unsigned int *)(*((_QWORD *)this + 25) + 32LL), &v20) >= 0 )
          {
            v12 = 0;
            if ( v20 )
            {
LABEL_14:
              if ( *(_DWORD *)(*((_QWORD *)this + 25) + 48LL) )
              {
                v13 = pv;
                for ( i = 0; ; ++i )
                {
                  v15 = *((_QWORD *)this + 25);
                  if ( i >= *(_DWORD *)(v15 + 48) )
                    break;
                  v19 = 0;
                  if ( (int)CSimpleStringArrayBase<CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>::Find(
                              *(_QWORD *)(v15 + 40) + 8 * (5LL * i + 1),
                              v13,
                              &v19) >= 0 )
                    goto LABEL_19;
                }
              }
              else
              {
LABEL_19:
                v16 = ILClone(v7);
                if ( !CAppListHelper::PostMessageW(*((CAppListHelper **)this + 25), v12 + 1034, 0, (__int64)v16) )
                  ILFree(v16);
              }
            }
          }
        }
        CoTaskMemFree(pv);
        goto LABEL_22;
      }
    }
  }
}

```

## disassembly

```asm
0x18025f6fc  mov     [rsp-28h+arg_0], rbx
0x18025f701  mov     [rsp-28h+arg_10], rsi
0x18025f706  mov     [rsp-28h+ppv], r9
0x18025f70b  push    rbp
0x18025f70c  push    rdi
0x18025f70d  push    r12
0x18025f70f  push    r14
0x18025f711  push    r15
0x18025f713  mov     rbp, rsp
0x18025f716  sub     rsp, 50h
0x18025f71a  mov     r15d, edx
0x18025f71d  mov     rsi, rcx
0x18025f720  cmp     edx, 2
0x18025f723  jz      short loc_18025F72E
0x18025f725  cmp     edx, 4
0x18025f728  jnz     loc_18025F8E4
0x18025f72e  mov     rcx, [rcx+0C8h]
0x18025f735  mov     rdx, r8; pidlChild
0x18025f738  mov     rcx, [rcx+18h]; pidlParent
0x18025f73c  call    cs:__imp_ILFindChild
0x18025f742  xor     r12d, r12d
0x18025f745  mov     r14, rax
0x18025f748  test    rax, rax
0x18025f74b  jz      loc_18025F8E4
0x18025f751  cmp     [rax], r12w
0x18025f755  jz      short loc_18025F769
0x18025f757  movzx   eax, word ptr [rax]
0x18025f75a  add     rax, r14
0x18025f75d  jz      short loc_18025F769
0x18025f75f  cmp     [rax], r12w
0x18025f763  jnz     loc_18025F8E4
0x18025f769  lea     rcx, [rbp+var_20]
0x18025f76d  mov     [rbp+var_20], r12
0x18025f771  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IImmersiveMonitor>>)
0x18025f776  mov     rcx, [rsi+0C8h]
0x18025f77d  lea     r9, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x18025f784  mov     r8, r14; pidl
0x18025f787  mov     [rsp+50h+ppvItem], rax; ppvItem
0x18025f78c  xor     edx, edx; psfParent
0x18025f78e  mov     rcx, [rcx+18h]; pidlParent
0x18025f792  call    cs:__imp_SHCreateItemWithParent
0x18025f798  test    eax, eax
0x18025f79a  js      loc_18025F8DB
0x18025f7a0  lea     rcx, [rbp+ppv]
0x18025f7a4  mov     [rbp+ppv], r12
0x18025f7a8  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18025f7ad  xor     edx, edx; pUnkOuter
0x18025f7af  lea     rax, [rbp+ppv]
0x18025f7b3  lea     r9, _GUID_d54e68c2_54cd_48b3_ad9a_3f4a4503ba80; riid
0x18025f7ba  mov     [rsp+50h+ppvItem], rax; ppv
0x18025f7bf  lea     rcx, CLSID_BackgroundTaskCapability; rclsid
0x18025f7c6  lea     r8d, [rdx+1]; dwClsContext
0x18025f7ca  call    cs:__imp_CoCreateInstance
0x18025f7d0  test    eax, eax
0x18025f7d2  js      loc_18025F8D2
0x18025f7d8  mov     rdi, [rbp+var_20]
0x18025f7dc  xor     ecx, ecx; pv
0x18025f7de  mov     [rbp+pv], r12
0x18025f7e2  mov     rax, [rdi]
0x18025f7e5  mov     rbx, [rax+88h]
0x18025f7ec  call    cs:__imp_CoTaskMemFree
0x18025f7f2  lea     r8, [rbp+pv]
0x18025f7f6  mov     rcx, rdi
0x18025f7f9  lea     rdx, PKEY_AppUserModel_ID
0x18025f800  mov     rax, rbx
0x18025f803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025f808  test    eax, eax
0x18025f80a  js      loc_18025F8C8
0x18025f810  mov     [rbp+arg_8], r12d
0x18025f814  cmp     r15d, 4
0x18025f818  jnz     short loc_18025F820
0x18025f81a  lea     edi, [r15-3]
0x18025f81e  jmp     short loc_18025F84D
0x18025f820  mov     r8, [rsi+0C8h]
0x18025f827  lea     r9, [rbp+arg_8]
0x18025f82b  mov     rdx, [rbp+ppv]
0x18025f82f  mov     rcx, [rbp+var_20]
0x18025f833  mov     r8d, [r8+20h]
0x18025f837  call    ?IsAppLockScreenCapable@@YAJPEAUIShellItem2@@PEAUIBackgroundTaskCapability@@W4LOCK_SCREEN_APPLICATION_CAPABILITIES@@PEAH@Z; IsAppLockScreenCapable(IShellItem2 *,IBackgroundTaskCapability *,LOCK_SCREEN_APPLICATION_CAPABILITIES,int *)
0x18025f83c  test    eax, eax
0x18025f83e  js      loc_18025F8C8
0x18025f844  mov     edi, r12d
0x18025f847  cmp     [rbp+arg_8], r12d
0x18025f84b  jz      short loc_18025F8C8
0x18025f84d  mov     rax, [rsi+0C8h]
0x18025f854  cmp     [rax+30h], r12d
0x18025f858  jz      short loc_18025F897
0x18025f85a  mov     r15, [rbp+pv]
0x18025f85e  mov     ebx, r12d
0x18025f861  mov     rdx, [rsi+0C8h]
0x18025f868  cmp     ebx, [rdx+30h]
0x18025f86b  jnb     short loc_18025F8C8
0x18025f86d  mov     eax, ebx
0x18025f86f  lea     r8, [rbp+var_10]
0x18025f873  mov     [rbp+var_10], r12
0x18025f877  lea     rcx, [rax+rax*4]
0x18025f87b  mov     rax, [rdx+28h]
0x18025f87f  lea     rcx, [rcx+1]
0x18025f883  mov     rdx, r15
0x18025f886  lea     rcx, [rax+rcx*8]
0x18025f88a  call    ?Find@?$CSimpleStringArrayBase@VCSimpleArrayCaseInsensitiveOrdinalStringCompareHelper@@@@QEBAJPEBGPEA_K_K@Z; CSimpleStringArrayBase<CSimpleArrayCaseInsensitiveOrdinalStringCompareHelper>::Find(ushort const *,unsigned __int64 *,unsigned __int64)
0x18025f88f  test    eax, eax
0x18025f891  jns     short loc_18025F897
0x18025f893  inc     ebx
0x18025f895  jmp     short loc_18025F861
0x18025f897  mov     rcx, r14; pidl
0x18025f89a  call    cs:__imp_ILClone
0x18025f8a0  mov     rcx, [rsi+0C8h]; this
0x18025f8a7  lea     edx, [rdi+40Ah]; unsigned int
0x18025f8ad  mov     r9, rax; __int64
0x18025f8b0  xor     r8d, r8d; unsigned __int64
0x18025f8b3  mov     rbx, rax
0x18025f8b6  call    ?PostMessageW@CAppListHelper@@QEAA_NI_K_J@Z; CAppListHelper::PostMessageW(uint,unsigned __int64,__int64)
0x18025f8bb  test    al, al
0x18025f8bd  jnz     short loc_18025F8C8
0x18025f8bf  mov     rcx, rbx; pidl
0x18025f8c2  call    cs:__imp_ILFree
0x18025f8c8  mov     rcx, [rbp+pv]; pv
0x18025f8cc  call    cs:__imp_CoTaskMemFree
0x18025f8d2  lea     rcx, [rbp+ppv]
0x18025f8d6  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18025f8db  lea     rcx, [rbp+var_20]
0x18025f8df  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18025f8e4  lea     r11, [rsp+50h+var_s0]
0x18025f8e9  mov     rbx, [r11+30h]
0x18025f8ed  mov     rsi, [r11+40h]
0x18025f8f1  mov     rsp, r11
0x18025f8f4  pop     r15
0x18025f8f6  pop     r14
0x18025f8f8  pop     r12
0x18025f8fa  pop     rdi
0x18025f8fb  pop     rbp
0x18025f8fc  retn
```
