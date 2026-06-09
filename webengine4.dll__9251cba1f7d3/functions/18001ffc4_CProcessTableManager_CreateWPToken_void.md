# CProcessTableManager::CreateWPToken(void)

- ea: `0x18001ffc4`
- end: `0x1800201ef`
- name: `?CreateWPToken@CProcessTableManager@@CAXXZ`
- size: `555`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180020634`
- `0x18002064c`

## callees

- `0x18001ffc4`
- `0x180020dcc`
- `0x1800234b4`
- `0x180026bfc`
- `0x180045f80`
- `0x180047010`
- `0x18004d030`
- `0x1800653c0`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180020037`
- `KERNEL32!lstrlenW` at `0x180020037`
- `KERNEL32!Sleep` at `0x1800201b7`
- `KERNEL32!Sleep` at `0x1800201b7`
- `KERNEL32!SwitchToThread` at `0x180020192`
- `KERNEL32!SwitchToThread` at `0x180020192`
- `USERENV!LoadUserProfileW` at `0x180020176`
- `USERENV!LoadUserProfileW` at `0x180020176`
- `ucrtbase_clr0400!_wcsicmp` at `0x180020063`
- `ucrtbase_clr0400!_wcsicmp` at `0x180020063`

## string_xrefs

- `0x180020052`: `registry`

## pseudocode

```c
void CProcessTableManager::CreateWPToken(void)
{
  __int64 v0; // rax
  unsigned __int16 *i; // rcx
  unsigned __int16 v2; // dx
  HANDLE v3; // rdi
  BOOL UserProfileW; // eax
  void *v5; // rcx
  int j; // ebx
  _PROFILEINFOW ProfileInfo; // [rsp+20h] [rbp-E8h] BYREF
  void *v8; // [rsp+58h] [rbp-B0h]
  unsigned __int16 v9[104]; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int16 v10[104]; // [rsp+138h] [rbp+30h] BYREF
  unsigned __int16 v11[104]; // [rsp+208h] [rbp+100h] BYREF

  if ( g_lTokenCreated < 1000 )
  {
    if ( _InterlockedIncrement(&g_lTokenCreated) == 1 )
    {
      memset_0(v9, 0, sizeof(v9));
      if ( lstrlenW(g_szUserName) <= 8
        || word_18008E410 != 58
        || (word_18008E410 = 0, _wcsicmp(g_szUserName, L"registry")) )
      {
        v0 = 104;
        for ( i = v9; --v0; ++i )
        {
          v2 = *(unsigned __int16 *)((char *)i + (char *)g_szUserName - (char *)v9);
          if ( !v2 )
            break;
          *i = v2;
        }
        *i = 0;
      }
      else
      {
        word_18008E410 = 58;
        GetCredentialFromRegistry(g_szUserName, v9, 0x68u);
      }
      UnEncryptPassword(v11, 0x68u);
      g_hToken = CRegAccount::CreateWorkerProcessToken(v9, v11, &g_pSid);
      XspSecureZeroMemory(v11, 0xD0u);
      v3 = g_hToken;
      if ( (char *)g_hToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v8 = 0;
        memset(&ProfileInfo.lpDefaultPath, 0, 32);
        memset_0(v10, 0, 0xC8u);
        GetUserNameFromToken(v3, v10, 100);
        ProfileInfo.lpProfilePath = v10;
        ProfileInfo.lpUserName = (LPWSTR)0x100000038LL;
        UserProfileW = LoadUserProfileW(g_hToken, (LPPROFILEINFOW)&ProfileInfo.lpUserName);
        v5 = g_hProfile;
        if ( UserProfileW )
          v5 = v8;
        g_hProfile = v5;
      }
      SwitchToThread();
      g_lTokenCreated = 1000;
    }
    else
    {
      for ( j = 0; j < 300; ++j )
      {
        if ( g_lTokenCreated >= 1000 )
          break;
        Sleep(0x64u);
      }
    }
  }
}

```

## disassembly

```asm
0x18001ffc4  mov     rax, rsp
0x18001ffc7  mov     [rax+8], rbx
0x18001ffcb  mov     [rax+10h], rdi
0x18001ffcf  mov     [rax+18h], r15
0x18001ffd3  push    rbp
0x18001ffd4  lea     rbp, [rax-1E8h]
0x18001ffdb  sub     rsp, 2E0h
0x18001ffe2  mov     rax, cs:__security_cookie
0x18001ffe9  xor     rax, rsp
0x18001ffec  mov     [rbp+1E0h+var_10], rax
0x18001fff3  cmp     cs:?g_lTokenCreated@@3JA, 3E8h; long g_lTokenCreated
0x18001fffd  jge     loc_1800201C7
0x180020003  mov     eax, 1
0x180020008  lock xadd cs:?g_lTokenCreated@@3JA, eax; long g_lTokenCreated
0x180020010  inc     eax
0x180020012  cmp     eax, 1
0x180020015  jnz     loc_1800201A4
0x18002001b  xor     edx, edx; Val
0x18002001d  lea     rcx, [rsp+2E0h+var_280]; void *
0x180020022  mov     r8d, 0D0h; Size
0x180020028  call    memset_0
0x18002002d  lea     rdi, ?g_szUserName@@3PAGA; "machine"
0x180020034  mov     rcx, rdi; lpString
0x180020037  call    cs:__imp_lstrlenW
0x18002003d  xor     ebx, ebx
0x18002003f  cmp     eax, 8
0x180020042  jle     short loc_180020088
0x180020044  lea     r15d, [rbx+3Ah]
0x180020048  cmp     cs:word_18008E410, r15w
0x180020050  jnz     short loc_180020088
0x180020052  lea     rdx, aRegistry; "registry"
0x180020059  mov     cs:word_18008E410, bx
0x180020060  mov     rcx, rdi; String1
0x180020063  call    cs:__imp__wcsicmp
0x180020069  test    eax, eax
0x18002006b  jnz     short loc_180020088
0x18002006d  lea     r8d, [rbx+68h]; unsigned int
0x180020071  mov     cs:word_18008E410, r15w
0x180020079  lea     rdx, [rsp+2E0h+var_280]; unsigned __int16 *
0x18002007e  mov     rcx, rdi; unsigned __int16 *
0x180020081  call    ?GetCredentialFromRegistry@@YAJPEBGPEAGK@Z; GetCredentialFromRegistry(ushort const *,ushort *,ulong)
0x180020086  jmp     short loc_1800200C3
0x180020088  lea     rdx, [rsp+2E0h+var_280]
0x18002008d  mov     eax, 68h ; 'h'
0x180020092  sub     rdi, rdx
0x180020095  lea     rcx, [rsp+2E0h+var_280]
0x18002009a  mov     r8, rax
0x18002009d  sub     rax, 1
0x1800200a1  jz      short loc_1800200B5
0x1800200a3  movzx   edx, word ptr [rdi+rcx]
0x1800200a7  test    dx, dx
0x1800200aa  jz      short loc_1800200B5
0x1800200ac  mov     [rcx], dx
0x1800200af  add     rcx, 2
0x1800200b3  jmp     short loc_18002009A
0x1800200b5  test    r8, r8
0x1800200b8  lea     rax, [rcx-2]
0x1800200bc  cmovnz  rax, rcx
0x1800200c0  mov     [rax], bx
0x1800200c3  mov     edx, 68h ; 'h'; unsigned int
0x1800200c8  lea     rcx, [rbp+1E0h+var_E0]; unsigned __int16 *
0x1800200cf  call    ?UnEncryptPassword@@YAXPEAGK@Z; UnEncryptPassword(ushort *,ulong)
0x1800200d4  lea     r8, ?g_pSid@@3PEAXEA; void **
0x1800200db  lea     rdx, [rbp+1E0h+var_E0]; unsigned __int16 *
0x1800200e2  lea     rcx, [rsp+2E0h+var_280]; unsigned __int16 *
0x1800200e7  call    ?CreateWorkerProcessToken@CRegAccount@@SAPEAXPEAG0PEAPEAX@Z; CRegAccount::CreateWorkerProcessToken(ushort *,ushort *,void * *)
0x1800200ec  mov     edx, 0D0h; unsigned __int64
0x1800200f1  mov     cs:?g_hToken@@3PEAXEA, rax; void * g_hToken
0x1800200f8  lea     rcx, [rbp+1E0h+var_E0]; void *
0x1800200ff  call    ?XspSecureZeroMemory@@YAXPEAX_K@Z; XspSecureZeroMemory(void *,unsigned __int64)
0x180020104  mov     rdi, cs:?g_hToken@@3PEAXEA; void * g_hToken
0x18002010b  lea     rax, [rdi-1]
0x18002010f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180020113  ja      short loc_180020192
0x180020115  xorps   xmm0, xmm0
0x180020118  lea     rcx, [rbp+1E0h+var_1B0]; void *
0x18002011c  xor     eax, eax
0x18002011e  xor     edx, edx; Val
0x180020120  mov     r8d, 0C8h; Size
0x180020126  mov     [rsp+2E0h+var_290], rax
0x18002012b  movups  xmmword ptr [rsp+2E0h+ProfileInfo.lpUserName], xmm0
0x180020130  movups  xmmword ptr [rsp+2E0h+ProfileInfo.lpDefaultPath], xmm0
0x180020135  movups  xmmword ptr [rsp+2E0h+ProfileInfo.lpPolicyPath], xmm0
0x18002013a  call    memset_0
0x18002013f  mov     r8d, 64h ; 'd'; int
0x180020145  lea     rdx, [rbp+1E0h+var_1B0]; unsigned __int16 *
0x180020149  mov     rcx, rdi; TokenHandle
0x18002014c  call    ?GetUserNameFromToken@@YAHPEAXPEAGH@Z; GetUserNameFromToken(void *,ushort *,int)
0x180020151  mov     rcx, cs:?g_hToken@@3PEAXEA; hToken
0x180020158  lea     rax, [rbp+1E0h+var_1B0]
0x18002015c  lea     rdx, [rsp+2E0h+ProfileInfo.lpUserName]; lpProfileInfo
0x180020161  mov     [rsp+2E0h+ProfileInfo.lpProfilePath], rax
0x180020166  mov     dword ptr [rsp+2E0h+ProfileInfo.lpUserName], 38h ; '8'
0x18002016e  mov     dword ptr [rsp+2E0h+ProfileInfo.lpUserName+4], 1
0x180020176  call    cs:__imp_LoadUserProfileW
0x18002017c  mov     rcx, cs:?g_hProfile@@3PEAXEA; void * g_hProfile
0x180020183  test    eax, eax
0x180020185  cmovnz  rcx, [rsp+2E0h+var_290]
0x18002018b  mov     cs:?g_hProfile@@3PEAXEA, rcx; void * g_hProfile
0x180020192  call    cs:__imp_SwitchToThread
0x180020198  mov     cs:?g_lTokenCreated@@3JA, 3E8h; long g_lTokenCreated
0x1800201a2  jmp     short loc_1800201C7
0x1800201a4  xor     ebx, ebx
0x1800201a6  cmp     cs:?g_lTokenCreated@@3JA, 3E8h; long g_lTokenCreated
0x1800201b0  jge     short loc_1800201C7
0x1800201b2  mov     ecx, 64h ; 'd'; dwMilliseconds
0x1800201b7  call    cs:__imp_Sleep
0x1800201bd  inc     ebx
0x1800201bf  cmp     ebx, 12Ch
0x1800201c5  jl      short loc_1800201A6
0x1800201c7  mov     rcx, [rbp+1E0h+var_10]
0x1800201ce  xor     rcx, rsp; StackCookie
0x1800201d1  call    __security_check_cookie
0x1800201d6  lea     r11, [rsp+2E0h+var_s0]
0x1800201de  mov     rbx, [r11+10h]
0x1800201e2  mov     rdi, [r11+18h]
0x1800201e6  mov     r15, [r11+20h]
0x1800201ea  mov     rsp, r11
0x1800201ed  pop     rbp
0x1800201ee  retn
```
