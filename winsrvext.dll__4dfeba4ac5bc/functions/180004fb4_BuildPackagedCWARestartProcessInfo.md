# BuildPackagedCWARestartProcessInfo

- ea: `0x180004fb4`
- end: `0x180005371`
- name: `BuildPackagedCWARestartProcessInfo`
- size: `957`
- prototype: `int __fastcall(HANDLE hProcess, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180007374`

## callees

- `0x180001d88`
- `0x180004fb4`
- `0x1800138ad`
- `0x1800138f0`

## import_xrefs

- `KERNELBASE!GetApplicationUserModelId` at `0x180005043`
- `KERNELBASE!GetApplicationUserModelId` at `0x180005075`
- `KERNELBASE!GetApplicationUserModelId` at `0x180005289`
- `KERNELBASE!GetApplicationUserModelId` at `0x180005043`
- `KERNELBASE!GetApplicationUserModelId` at `0x180005075`
- `KERNELBASE!GetApplicationUserModelId` at `0x180005289`
- `KERNELBASE!LocalAlloc` at `0x180005243`
- `KERNELBASE!LocalAlloc` at `0x180005243`
- `ntdll!NtSetInformationThread` at `0x1800051b5`
- `ntdll!NtSetInformationThread` at `0x1800051db`
- `ntdll!NtSetInformationThread` at `0x1800051b5`
- `ntdll!NtSetInformationThread` at `0x1800051db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005327`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005327`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800050e5`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800050e5`
- `api-ms-win-core-windowserrorreporting-l1-1-0!GetApplicationRestartSettings` at `0x1800050a6`
- `api-ms-win-core-windowserrorreporting-l1-1-0!GetApplicationRestartSettings` at `0x18000530d`
- `api-ms-win-core-windowserrorreporting-l1-1-0!GetApplicationRestartSettings` at `0x1800050a6`
- `api-ms-win-core-windowserrorreporting-l1-1-0!GetApplicationRestartSettings` at `0x18000530d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005175`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005175`
- `ext-ms-win-desktopappx-l1-1-3!GetApplicationExecutableRelativePath` at `0x18000513d`
- `ext-ms-win-desktopappx-l1-1-3!GetApplicationExecutableRelativePath` at `0x18000513d`

## pseudocode

```c
int __fastcall BuildPackagedCWARestartProcessInfo(HANDLE hProcess, __int64 a2, _QWORD *a3)
{
  int result; // eax
  bool v6; // sf
  __int64 v7; // rcx
  WCHAR *v8; // rcx
  WCHAR *v9; // rdx
  WCHAR v10; // ax
  __int64 v11; // rax
  NTSTATUS v12; // eax
  UINT32 v13; // edx
  unsigned int v14; // ecx
  unsigned int v15; // edx
  unsigned __int64 v16; // rax
  char *v17; // rax
  _WORD *v18; // rdi
  __int128 v19; // xmm0
  LONG v20; // eax
  int ApplicationRestartSettings; // ebx
  __int64 v22; // rdx
  int v23; // ebx
  __int64 v24; // r8
  DWORD dwSize; // [rsp+28h] [rbp-E0h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+2Ch] [rbp-DCh] BYREF
  DWORD pcchSize[2]; // [rsp+30h] [rbp-D8h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-D0h] BYREF
  __int64 ThreadInformation; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+48h] [rbp-C0h] BYREF
  __m256i v31; // [rsp+60h] [rbp-A8h]
  WCHAR applicationUserModelId[136]; // [rsp+88h] [rbp-80h] BYREF
  WCHAR Src[264]; // [rsp+198h] [rbp+90h] BYREF
  WCHAR ExeName[264]; // [rsp+3A8h] [rbp+2A0h] BYREF

  ThreadInformation = a2;
  *a3 = 0;
  pcchSize[1] = 0;
  v31 = *(__m256i *)L"CWALauncher.exe";
  pcchSize[0] = 0;
  applicationUserModelIdLength = 0;
  dwSize = 0;
  pv = 0;
  v30 = 0;
  result = GetApplicationUserModelId(hProcess, &applicationUserModelIdLength, 0);
  if ( result == 122 )
  {
    result = GetApplicationUserModelId(hProcess, &applicationUserModelIdLength, applicationUserModelId);
    v6 = result < 0;
    if ( result > 0 )
    {
      result = (unsigned __int16)result | 0x80070000;
      v6 = result < 0;
    }
    if ( !v6 )
    {
      result = GetApplicationRestartSettings(hProcess, 0, pcchSize, &pcchSize[1]);
      if ( result >= 0 )
      {
        if ( (pcchSize[1] & 8) != 0 )
        {
          return 0;
        }
        else
        {
          dwSize = 260;
          if ( QueryFullProcessImageNameW(hProcess, 0, ExeName, &dwSize) )
          {
            ++dwSize;
            if ( (unsigned __int8)IsGetApplicationExecutableRelativePathPresent(v7) )
            {
              result = GetApplicationExecutableRelativePath(hProcess, applicationUserModelId, ExeName, &pv);
              if ( result >= 0 )
              {
                v8 = (WCHAR *)pv;
                v9 = Src;
                do
                {
                  v10 = *v8++;
                  *v9++ = v10;
                }
                while ( v10 );
                CoTaskMemFree(pv);
                v11 = -1;
                do
                  ++v11;
                while ( Src[v11] );
                dwSize = v11 + 1;
                v12 = NtSetInformationThread(
                        (HANDLE)0xFFFFFFFFFFFFFFFELL,
                        ThreadImpersonationToken,
                        &ThreadInformation,
                        8u);
                if ( v12 >= 0 )
                {
                  NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &v30, 8u);
                  v13 = applicationUserModelIdLength + 24;
                  if ( applicationUserModelIdLength >= 0xFFFFFFE8 )
                    return -2147024362;
                  v14 = v13 + dwSize;
                  if ( v13 + dwSize < v13 )
                    return -2147024362;
                  v15 = v14 + 2;
                  if ( v14 + 2 < v14 )
                    return -2147024362;
                  if ( v15 + pcchSize[0] < v15 )
                    return -2147024362;
                  v16 = 2LL * (v15 + pcchSize[0]);
                  if ( v16 > 0xFFFFFFFF || (int)v16 + 16 < (unsigned int)v16 )
                  {
                    return -2147024362;
                  }
                  else
                  {
                    v17 = (char *)LocalAlloc(0x40u, (unsigned int)(v16 + 16));
                    v18 = v17;
                    if ( v17 )
                    {
                      v19 = *(_OWORD *)((char *)&v31.m256i_u64[1] + 6);
                      *((_OWORD *)v17 + 1) = *(_OWORD *)L"PackagedCWALauncher.exe";
                      *((_OWORD *)v17 + 2) = *(_OWORD *)L"CWALauncher.exe";
                      *(_OWORD *)(v17 + 46) = v19;
                      *((_WORD *)v17 + 31) = 32;
                      v20 = GetApplicationUserModelId(hProcess, &applicationUserModelIdLength, (PWSTR)v17 + 32);
                      ApplicationRestartSettings = v20;
                      if ( v20 > 0 )
                        ApplicationRestartSettings = (unsigned __int16)v20 | 0x80070000;
                      v22 = applicationUserModelIdLength + 24;
                      v18[applicationUserModelIdLength + 31] = 32;
                      if ( ApplicationRestartSettings < 0
                        || (v23 = v22 + 1,
                            v18[v22 + 8] = 34,
                            memcpy_0(&v18[(unsigned int)(v22 + 1) + 8], Src, 2LL * dwSize),
                            v24 = v23 + dwSize,
                            v18[(unsigned int)(v24 - 1) + 8] = 34,
                            v18[v24 + 8] = 32,
                            ApplicationRestartSettings = GetApplicationRestartSettings(
                                                           hProcess,
                                                           &v18[(unsigned int)(v24 + 1) + 8],
                                                           pcchSize,
                                                           0),
                            ApplicationRestartSettings < 0) )
                      {
                        LocalFree(v18);
                      }
                      else
                      {
                        *a3 = v18;
                      }
                      return ApplicationRestartSettings;
                    }
                    else
                    {
                      return -2147024882;
                    }
                  }
                }
                else
                {
                  return v12 | 0x10000000;
                }
              }
            }
            else
            {
              return -2147023728;
            }
          }
          else
          {
            result = GetLastError();
            if ( result > 0 )
              return (unsigned __int16)result | 0x80070000;
          }
        }
      }
    }
  }
  else if ( result > 0 )
  {
    return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180004fb4  mov     rax, rsp
0x180004fb7  mov     [rax+20h], rbx
0x180004fbb  push    rbp
0x180004fbc  push    rsi
0x180004fbd  push    rdi
0x180004fbe  push    r12
0x180004fc0  push    r13
0x180004fc2  push    r14
0x180004fc4  push    r15
0x180004fc6  lea     rbp, [rax-518h]
0x180004fcd  sub     rsp, 5E0h
0x180004fd4  movaps  xmmword ptr [rax-48h], xmm6
0x180004fd8  movaps  xmmword ptr [rax-58h], xmm7
0x180004fdc  mov     rax, cs:__security_cookie
0x180004fe3  xor     rax, rsp
0x180004fe6  mov     [rbp+510h+var_60], rax
0x180004fed  movups  xmm6, xmmword ptr cs:aPackagedcwalau+10h; "CWALauncher.exe"
0x180004ff4  xor     r12d, r12d
0x180004ff7  mov     r15, r8
0x180004ffa  movups  xmm0, xmmword ptr cs:aPackagedcwalau+20h; "her.exe"
0x180005001  mov     [rsp+610h+ThreadInformation], rdx
0x180005006  lea     rdx, [rsp+610h+applicationUserModelIdLength]; applicationUserModelIdLength
0x18000500b  movups  xmm7, xmmword ptr cs:aPackagedcwalau; "PackagedCWALauncher.exe"
0x180005012  mov     [r8], r12
0x180005015  mov     r14, rcx
0x180005018  xor     r8d, r8d; applicationUserModelId
0x18000501b  mov     [rsp+610h+pcchSize+4], r12d
0x180005020  movups  [rsp+610h+var_5C0+8], xmm6
0x180005025  mov     [rsp+610h+pcchSize], r12d
0x18000502a  movups  [rsp+610h+var_5B0+8], xmm0
0x18000502f  mov     [rsp+610h+applicationUserModelIdLength], r12d
0x180005034  mov     [rsp+610h+dwSize], r12d
0x180005039  mov     [rsp+610h+pv], r12
0x18000503e  mov     [rsp+610h+var_5D0], r12
0x180005043  call    cs:__imp_GetApplicationUserModelId
0x18000504a  nop     dword ptr [rax+rax+00h]
0x18000504f  cmp     eax, 7Ah ; 'z'
0x180005052  jz      short loc_180005069
0x180005054  test    eax, eax
0x180005056  jle     loc_18000533C
0x18000505c  movzx   eax, ax
0x18000505f  or      eax, 80070000h
0x180005064  jmp     loc_18000533C
0x180005069  lea     r8, [rbp+510h+applicationUserModelId]; applicationUserModelId
0x18000506d  mov     rcx, r14; hProcess
0x180005070  lea     rdx, [rsp+610h+applicationUserModelIdLength]; applicationUserModelIdLength
0x180005075  call    cs:__imp_GetApplicationUserModelId
0x18000507c  nop     dword ptr [rax+rax+00h]
0x180005081  mov     esi, 80070000h
0x180005086  test    eax, eax
0x180005088  jle     short loc_180005091
0x18000508a  movzx   eax, ax
0x18000508d  or      eax, esi
0x18000508f  test    eax, eax
0x180005091  js      loc_18000533C
0x180005097  lea     r9, [rsp+610h+pcchSize+4]; pdwFlags
0x18000509c  xor     edx, edx; pwzCommandline
0x18000509e  lea     r8, [rsp+610h+pcchSize]; pcchSize
0x1800050a3  mov     rcx, r14; hProcess
0x1800050a6  call    cs:__imp_GetApplicationRestartSettings
0x1800050ad  nop     dword ptr [rax+rax+00h]
0x1800050b2  test    eax, eax
0x1800050b4  js      loc_18000533C
0x1800050ba  mov     ebx, 8
0x1800050bf  test    byte ptr [rsp+610h+pcchSize+4], bl
0x1800050c3  jz      short loc_1800050CC
0x1800050c5  xor     eax, eax
0x1800050c7  jmp     loc_18000533C
0x1800050cc  lea     r9, [rsp+610h+dwSize]; lpdwSize
0x1800050d1  mov     [rsp+610h+dwSize], 104h
0x1800050d9  lea     r8, [rbp+510h+ExeName]; lpExeName
0x1800050e0  xor     edx, edx; dwFlags
0x1800050e2  mov     rcx, r14; hProcess
0x1800050e5  call    cs:__imp_QueryFullProcessImageNameW
0x1800050ec  nop     dword ptr [rax+rax+00h]
0x1800050f1  test    eax, eax
0x1800050f3  jnz     short loc_180005113
0x1800050f5  call    cs:__imp_GetLastError
0x1800050fc  nop     dword ptr [rax+rax+00h]
0x180005101  test    eax, eax
0x180005103  jle     loc_18000533C
0x180005109  movzx   eax, ax
0x18000510c  or      eax, esi
0x18000510e  jmp     loc_18000533C
0x180005113  inc     [rsp+610h+dwSize]
0x180005117  call    IsGetApplicationExecutableRelativePathPresent
0x18000511c  test    al, al
0x18000511e  jnz     short loc_18000512A
0x180005120  mov     eax, 80070490h
0x180005125  jmp     loc_18000533C
0x18000512a  lea     r9, [rsp+610h+pv]
0x18000512f  mov     rcx, r14
0x180005132  lea     r8, [rbp+510h+ExeName]
0x180005139  lea     rdx, [rbp+510h+applicationUserModelId]
0x18000513d  call    cs:__imp_GetApplicationExecutableRelativePath
0x180005144  nop     dword ptr [rax+rax+00h]
0x180005149  test    eax, eax
0x18000514b  js      loc_18000533C
0x180005151  mov     rcx, [rsp+610h+pv]
0x180005156  lea     rdx, [rbp+510h+Src]
0x18000515d  movzx   eax, word ptr [rcx]
0x180005160  lea     rcx, [rcx+2]
0x180005164  mov     [rdx], ax
0x180005167  lea     rdx, [rdx+2]
0x18000516b  test    ax, ax
0x18000516e  jnz     short loc_18000515D
0x180005170  mov     rcx, [rsp+610h+pv]; pv
0x180005175  call    cs:__imp_CoTaskMemFree
0x18000517c  nop     dword ptr [rax+rax+00h]
0x180005181  lea     rcx, [rbp+510h+Src]
0x180005188  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000518c  inc     rax
0x18000518f  cmp     [rcx+rax*2], r12w
0x180005194  jnz     short loc_18000518C
0x180005196  inc     eax
0x180005198  lea     r8, [rsp+610h+ThreadInformation]; ThreadInformation
0x18000519d  mov     edi, 5
0x1800051a2  mov     [rsp+610h+dwSize], eax
0x1800051a6  mov     r13, 0FFFFFFFFFFFFFFFEh
0x1800051ad  mov     edx, edi; ThreadInformationClass
0x1800051af  mov     rcx, r13; ThreadHandle
0x1800051b2  mov     r9d, ebx; ThreadInformationLength
0x1800051b5  call    cs:__imp_NtSetInformationThread
0x1800051bc  nop     dword ptr [rax+rax+00h]
0x1800051c1  test    eax, eax
0x1800051c3  jns     short loc_1800051CE
0x1800051c5  bts     eax, 1Ch
0x1800051c9  jmp     loc_18000533C
0x1800051ce  mov     r9d, ebx; ThreadInformationLength
0x1800051d1  lea     r8, [rsp+610h+var_5D0]; ThreadInformation
0x1800051d6  mov     edx, edi; ThreadInformationClass
0x1800051d8  mov     rcx, r13; ThreadHandle
0x1800051db  call    cs:__imp_NtSetInformationThread
0x1800051e2  nop     dword ptr [rax+rax+00h]
0x1800051e7  mov     edx, [rsp+610h+applicationUserModelIdLength]
0x1800051eb  add     edx, 18h
0x1800051ee  cmp     edx, 18h
0x1800051f1  jb      loc_180005337
0x1800051f7  mov     ecx, [rsp+610h+dwSize]
0x1800051fb  add     ecx, edx
0x1800051fd  cmp     ecx, edx
0x1800051ff  jb      loc_180005337
0x180005205  lea     edx, [rcx+2]
0x180005208  cmp     edx, ecx
0x18000520a  jb      loc_180005337
0x180005210  mov     ecx, [rsp+610h+pcchSize]
0x180005214  add     ecx, edx
0x180005216  cmp     ecx, edx
0x180005218  jb      loc_180005337
0x18000521e  mov     eax, ecx
0x180005220  mov     ecx, 0FFFFFFFFh
0x180005225  add     rax, rax
0x180005228  cmp     rax, rcx
0x18000522b  ja      loc_180005337
0x180005231  lea     ecx, [rax+10h]
0x180005234  cmp     ecx, eax
0x180005236  jb      loc_180005337
0x18000523c  mov     edx, ecx; uBytes
0x18000523e  mov     ecx, 40h ; '@'; uFlags
0x180005243  call    cs:__imp_LocalAlloc
0x18000524a  nop     dword ptr [rax+rax+00h]
0x18000524f  mov     rdi, rax
0x180005252  test    rax, rax
0x180005255  jnz     short loc_180005261
0x180005257  mov     eax, 8007000Eh
0x18000525c  jmp     loc_18000533C
0x180005261  movups  xmm0, [rsp+610h+var_5B0+6]
0x180005266  mov     r13d, 20h ; ' '
0x18000526c  lea     r8, [rax+40h]; applicationUserModelId
0x180005270  movups  xmmword ptr [rax+10h], xmm7
0x180005274  lea     rdx, [rsp+610h+applicationUserModelIdLength]; applicationUserModelIdLength
0x180005279  mov     rcx, r14; hProcess
0x18000527c  movups  xmmword ptr [rax+20h], xmm6
0x180005280  movups  xmmword ptr [rax+2Eh], xmm0
0x180005284  mov     [rax+3Eh], r13w
0x180005289  call    cs:__imp_GetApplicationUserModelId
0x180005290  nop     dword ptr [rax+rax+00h]
0x180005295  mov     ebx, eax
0x180005297  test    eax, eax
0x180005299  jle     short loc_1800052A0
0x18000529b  movzx   ebx, ax
0x18000529e  or      ebx, esi
0x1800052a0  mov     edx, [rsp+610h+applicationUserModelIdLength]
0x1800052a4  add     edx, 18h
0x1800052a7  lea     eax, [rdx-1]
0x1800052aa  mov     [rdi+rax*2+10h], r13w
0x1800052b0  test    ebx, ebx
0x1800052b2  js      short loc_180005324
0x1800052b4  lea     ebx, [rdx+1]
0x1800052b7  mov     esi, 22h ; '"'
0x1800052bc  mov     [rdi+rdx*2+10h], si
0x1800052c1  lea     rdx, [rbp+510h+Src]; Src
0x1800052c8  mov     r8d, [rsp+610h+dwSize]
0x1800052cd  mov     eax, ebx
0x1800052cf  add     r8, r8; Size
0x1800052d2  add     rax, 8
0x1800052d6  lea     rcx, [rdi+rax*2]; void *
0x1800052da  call    memcpy_0
0x1800052df  mov     r8d, [rsp+610h+dwSize]
0x1800052e4  xor     r9d, r9d; pdwFlags
0x1800052e7  add     r8d, ebx
0x1800052ea  mov     rcx, r14; hProcess
0x1800052ed  lea     eax, [r8-1]
0x1800052f1  lea     edx, [r8+1]
0x1800052f5  mov     [rdi+rax*2+10h], si
0x1800052fa  lea     rdx, [rdx+8]
0x1800052fe  mov     [rdi+r8*2+10h], r13w
0x180005304  lea     rdx, [rdi+rdx*2]; pwzCommandline
0x180005308  lea     r8, [rsp+610h+pcchSize]; pcchSize
0x18000530d  call    cs:__imp_GetApplicationRestartSettings
0x180005314  nop     dword ptr [rax+rax+00h]
0x180005319  mov     ebx, eax
0x18000531b  test    eax, eax
0x18000531d  js      short loc_180005324
0x18000531f  mov     [r15], rdi
0x180005322  jmp     short loc_180005333
0x180005324  mov     rcx, rdi; hMem
0x180005327  call    cs:__imp_LocalFree
0x18000532e  nop     dword ptr [rax+rax+00h]
0x180005333  mov     eax, ebx
0x180005335  jmp     short loc_18000533C
0x180005337  mov     eax, 80070216h
0x18000533c  mov     rcx, [rbp+510h+var_60]
0x180005343  xor     rcx, rsp; StackCookie
0x180005346  call    __security_check_cookie
0x18000534b  lea     r11, [rsp+610h+var_30]
0x180005353  mov     rbx, [r11+58h]
0x180005357  movaps  xmm6, xmmword ptr [r11-10h]
0x18000535c  movaps  xmm7, xmmword ptr [r11-20h]
0x180005361  mov     rsp, r11
0x180005364  pop     r15
0x180005366  pop     r14
0x180005368  pop     r13
0x18000536a  pop     r12
0x18000536c  pop     rdi
0x18000536d  pop     rsi
0x18000536e  pop     rbp
0x18000536f  retn
```
