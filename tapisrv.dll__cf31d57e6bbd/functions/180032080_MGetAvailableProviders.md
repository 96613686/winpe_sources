# MGetAvailableProviders

- ea: `0x180032080`
- end: `0x180032504`
- name: `MGetAvailableProviders`
- size: `1156`
- prototype: `unsigned int __fastcall(__int64, _DWORD *, unsigned int, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callers

- `0x180028100`

## callees

- `0x180001600`
- `0x180001f50`
- `0x18001c740`
- `0x18002c8d4`
- `0x180031650`
- `0x180032080`
- `0x18003dc84`
- `0x18003fb7c`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x1800322b3`
- `RPCRT4!RpcRevertToSelf` at `0x1800322b3`
- `RPCRT4!RpcImpersonateClient` at `0x18003225c`
- `RPCRT4!RpcImpersonateClient` at `0x18003225c`
- `KERNEL32!GetSystemDirectoryW` at `0x180032128`
- `KERNEL32!GetSystemDirectoryW` at `0x180032128`
- `KERNEL32!FindClose` at `0x180032254`
- `KERNEL32!FindClose` at `0x180032291`
- `KERNEL32!FindClose` at `0x180032254`
- `KERNEL32!FindClose` at `0x180032291`
- `KERNEL32!FindNextFileW` at `0x180032243`
- `KERNEL32!FindNextFileW` at `0x180032243`
- `KERNEL32!FindFirstFileW` at `0x180032152`
- `KERNEL32!FindFirstFileW` at `0x180032152`
- `KERNEL32!HeapAlloc` at `0x1800321e5`
- `KERNEL32!HeapAlloc` at `0x1800321e5`
- `KERNEL32!FreeLibrary` at `0x1800323e8`
- `KERNEL32!FreeLibrary` at `0x1800323e8`
- `KERNEL32!GetProcAddress` at `0x180032388`
- `KERNEL32!GetProcAddress` at `0x1800323a6`
- `KERNEL32!GetProcAddress` at `0x1800323bb`
- `KERNEL32!GetProcAddress` at `0x1800323d5`
- `KERNEL32!GetProcAddress` at `0x180032388`
- `KERNEL32!GetProcAddress` at `0x1800323a6`
- `KERNEL32!GetProcAddress` at `0x1800323bb`
- `KERNEL32!GetProcAddress` at `0x1800323d5`
- `KERNEL32!LoadLibraryW` at `0x180032334`
- `KERNEL32!LoadLibraryW` at `0x180032334`
- `KERNEL32!GetLastError` at `0x180032161`
- `KERNEL32!GetLastError` at `0x180032161`

## string_xrefs

- `0x180032269`: `MGetAvailableProviders: RpcImpersonateClient err=%d`
- `0x18003237e`: `TSPI_providerInstall`
- `0x1800323b1`: `TUISPI_providerConfig`
- `0x180032395`: `TSPI_providerConfig`
- `0x1800323cb`: `TSPI_providerRemove`

## pseudocode

```c
unsigned int __fastcall MGetAvailableProviders(__int64 a1, _DWORD *a2, unsigned int a3, __int64 a4, unsigned int *a5)
{
  unsigned int v7; // r12d
  unsigned int result; // eax
  HANDLE FirstFileW; // r15
  DWORD LastError; // eax
  char *v12; // rbx
  unsigned int v13; // esi
  unsigned int v14; // r13d
  __int64 v15; // rax
  unsigned int v16; // eax
  char *v17; // rax
  char *v18; // r12
  RPC_STATUS v19; // eax
  unsigned int ProviderFriendlyName; // r15d
  char *v21; // rdx
  unsigned int v22; // eax
  unsigned int *v23; // r15
  const WCHAR *v24; // r12
  char *v25; // r13
  int v26; // esi
  unsigned int i; // eax
  HMODULE LibraryW; // rax
  HMODULE v29; // rsi
  __int64 v30; // rax
  const WCHAR *v31; // r12
  __int64 v32; // rax
  __int64 v33; // rcx
  unsigned int v34; // ecx
  __int64 v35; // rax
  __int64 v36; // rcx
  unsigned int v37; // ecx
  __int64 v38; // rax
  unsigned __int64 v39; // rax
  unsigned int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  unsigned int v42; // [rsp+24h] [rbp-DCh]
  unsigned int v43; // [rsp+24h] [rbp-DCh]
  unsigned int v44; // [rsp+28h] [rbp-D8h]
  char *lpMem; // [rsp+30h] [rbp-D0h]
  int v46; // [rsp+38h] [rbp-C8h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[272]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v7 = 0;
  lpMem = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  result = a2[3];
  if ( result <= a3 )
  {
    if ( result >= 0x18 )
    {
      *(_DWORD *)(a4 + 8) = 24;
      *(_DWORD *)(a4 + 4) = 24;
      *(_DWORD *)a4 = result;
      *(_QWORD *)(a4 + 16) = 0;
      *(_DWORD *)(a4 + 12) = 0;
      a2[3] = 0;
      GetSystemDirectoryW(Buffer, 0x104u);
      StringCbCatW(Buffer, 0x218u, L"\\*.TSP");
      FirstFileW = FindFirstFileW(Buffer, &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        TRACELogPrint(65538, "MGetAvailableProviders: FindFirstFile err=%d", LastError);
      }
      else
      {
        v12 = 0;
        v44 = 0;
        v13 = 0;
        v14 = 0;
        do
        {
          TRACELogPrint(262146, "MGetAvailableProviders: found '%ws'", FindFileData.cFileName);
          v15 = -1;
          do
            ++v15;
          while ( FindFileData.cFileName[v15] );
          v16 = 2 * v15 + 2;
          v42 = v16;
          v40 = v16 + v13;
          if ( v16 + v13 > v14 )
          {
            v14 += 512;
            v17 = (char *)HeapAlloc(ghTapisrvHeap, 8u, v14);
            v18 = v17;
            if ( !v17 )
            {
              result = FindClose(FirstFileW);
              *a2 = -2147483580;
              return result;
            }
            if ( v13 )
            {
              memcpy_0(v17, v12, v13);
              ServerFree(v12);
            }
            v16 = v42;
            v12 = v18;
            v7 = v44;
          }
          memcpy_0(&v12[v13], FindFileData.cFileName, v16);
          v13 = v40;
          v44 = ++v7;
        }
        while ( FindNextFileW(FirstFileW, &FindFileData) );
        FindClose(FirstFileW);
        v19 = RpcImpersonateClient(0);
        if ( v19 )
        {
          TRACELogPrint(65538, "MGetAvailableProviders: RpcImpersonateClient err=%d", v19);
          *a2 = -2147483576;
          return ServerFree(v12);
        }
        ProviderFriendlyName = GetProviderFriendlyName((LPCWSTR)v12);
        RpcRevertToSelf();
        if ( ProviderFriendlyName )
        {
          v21 = 0;
        }
        else
        {
          v21 = v12;
          lpMem = v12;
          ProviderFriendlyName = v40;
        }
        v46 = 20 * v7;
        v22 = v40 + ProviderFriendlyName + 20 * v7 + *(_DWORD *)(a4 + 4);
        *(_DWORD *)(a4 + 4) = v22;
        if ( v22 <= *(_DWORD *)a4 )
        {
          *(_DWORD *)(a4 + 8) += 20 * v7;
          v23 = (unsigned int *)(a4 + 24);
          v24 = (const WCHAR *)v12;
          v41 = 0;
          v25 = v21;
          v26 = 0;
          for ( i = 0; ; i = v43 + 1 )
          {
            v43 = i;
            if ( i >= v44 )
              break;
            if ( !v24 || !v25 )
            {
              TRACELogPrint(65538, "file name or friendly name empty for %d provider", i);
              break;
            }
            LibraryW = LoadLibraryW(v24);
            v29 = LibraryW;
            if ( LibraryW )
            {
              v23[4] = GetProcAddress(LibraryW, "TSPI_providerInstall") != 0;
              if ( GetProcAddress(v29, "TSPI_providerConfig") || GetProcAddress(v29, "TUISPI_providerConfig") )
                v23[4] |= 2u;
              if ( GetProcAddress(v29, "TSPI_providerRemove") )
                v23[4] |= 4u;
              FreeLibrary(v29);
              v33 = -1;
              do
                ++v33;
              while ( v24[v33] );
              v34 = 2 * v33 + 2;
              *v23 = v34;
              v35 = *(unsigned int *)(a4 + 8);
              v23[1] = v35;
              memcpy_0((void *)(a4 + v35), v24, v34);
              *(_DWORD *)(a4 + 8) += *v23;
              v36 = -1;
              v24 += (unsigned __int64)*v23 >> 1;
              do
                ++v36;
              while ( *(_WORD *)&v25[2 * v36] );
              v37 = 2 * v36 + 2;
              v23[2] = v37;
              v38 = *(unsigned int *)(a4 + 8);
              v23[3] = v38;
              memcpy_0((void *)(a4 + v38), v25, v37);
              *(_DWORD *)(a4 + 8) += v23[2];
              v39 = (unsigned __int64)v23[2] >> 1;
              v26 = ++v41;
              v23 += 5;
              v25 += 2 * v39;
            }
            else
            {
              v30 = -1;
              do
                ++v30;
              while ( v24[v30] );
              v31 = &v24[v30];
              v32 = -1;
              v24 = v31 + 1;
              do
                ++v32;
              while ( *(_WORD *)&v25[2 * v32] );
              v26 = v41;
              v25 += 2 * v32 + 2;
            }
          }
          *(_DWORD *)(a4 + 16) = v46;
          *(_DWORD *)(a4 + 12) = v26;
          *(_DWORD *)(a4 + 20) = 24;
        }
        ServerFree(v12);
        if ( lpMem != v12 )
          ServerFree(lpMem);
      }
      result = *(_DWORD *)(a4 + 8) + 60;
      *a5 = result;
      *a2 = 0;
    }
    else
    {
      *a2 = -2147483571;
    }
  }
  else
  {
    *a2 = -2147483576;
  }
  return result;
}

```

## disassembly

```asm
0x180032080  mov     [rsp-8+arg_0], rbx
0x180032085  push    rbp
0x180032086  push    rsi
0x180032087  push    rdi
0x180032088  push    r12
0x18003208a  push    r13
0x18003208c  push    r14
0x18003208e  push    r15
0x180032090  lea     rbp, [rsp-3D0h]
0x180032098  sub     rsp, 4D0h
0x18003209f  mov     rax, cs:__security_cookie
0x1800320a6  xor     rax, rsp
0x1800320a9  mov     [rbp+400h+var_40], rax
0x1800320b0  mov     rax, [rbp+400h+arg_20]
0x1800320b7  lea     rcx, [rsp+500h+FindFileData]; void *
0x1800320bc  mov     ebx, r8d
0x1800320bf  mov     [rsp+500h+var_4C0], rax
0x1800320c4  mov     r14, rdx
0x1800320c7  xor     r12d, r12d
0x1800320ca  xor     edx, edx; Val
0x1800320cc  mov     [rsp+500h+lpMem], r12
0x1800320d1  mov     r8d, 250h; Size
0x1800320d7  mov     rdi, r9
0x1800320da  call    memset_0
0x1800320df  mov     eax, [r14+0Ch]
0x1800320e3  cmp     eax, ebx
0x1800320e5  jbe     short loc_1800320F3
0x1800320e7  mov     dword ptr [r14], 80000048h
0x1800320ee  jmp     loc_1800324DA
0x1800320f3  mov     ecx, 18h
0x1800320f8  cmp     eax, ecx
0x1800320fa  jnb     short loc_180032108
0x1800320fc  mov     dword ptr [r14], 8000004Dh
0x180032103  jmp     loc_1800324DA
0x180032108  mov     [rdi+8], ecx
0x18003210b  mov     edx, 104h; uSize
0x180032110  mov     [rdi+4], ecx
0x180032113  lea     rcx, [rbp+400h+Buffer]; lpBuffer
0x18003211a  mov     [rdi], eax
0x18003211c  mov     [rdi+10h], r12
0x180032120  mov     [rdi+0Ch], r12d
0x180032124  mov     [r14+0Ch], r12d
0x180032128  call    cs:__imp_GetSystemDirectoryW
0x18003212e  lea     r8, aTsp; "\\*.TSP"
0x180032135  mov     edx, 218h; cbDest
0x18003213a  lea     rcx, [rbp+400h+Buffer]; pszDest
0x180032141  call    StringCbCatW
0x180032146  lea     rdx, [rsp+500h+FindFileData]; lpFindFileData
0x18003214b  lea     rcx, [rbp+400h+Buffer]; lpFileName
0x180032152  call    cs:__imp_FindFirstFileW
0x180032158  mov     r15, rax
0x18003215b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003215f  jnz     short loc_180032180
0x180032161  call    cs:__imp_GetLastError
0x180032167  lea     rdx, aMgetavailablep_1; "MGetAvailableProviders: FindFirstFile e"...
0x18003216e  mov     ecx, 10002h
0x180032173  mov     r8d, eax
0x180032176  call    TRACELogPrint
0x18003217b  jmp     loc_1800324CA
0x180032180  mov     rbx, r12
0x180032183  mov     [rsp+500h+var_4D8], r12d
0x180032188  mov     esi, r12d
0x18003218b  mov     r13d, r12d
0x18003218e  lea     r8, [rsp+500h+FindFileData.cFileName]
0x180032193  mov     ecx, 40002h
0x180032198  lea     rdx, aMgetavailablep; "MGetAvailableProviders: found '%ws'"
0x18003219f  call    TRACELogPrint
0x1800321a4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800321a8  lea     rdx, [rsp+500h+FindFileData.cFileName]
0x1800321ad  xor     ecx, ecx
0x1800321af  inc     rax
0x1800321b2  cmp     [rdx+rax*2], cx
0x1800321b6  jnz     short loc_1800321AF
0x1800321b8  lea     eax, ds:2[rax*2]
0x1800321bf  lea     ecx, [rax+rsi]
0x1800321c2  mov     [rsp+500h+var_4DC], eax
0x1800321c6  mov     [rsp+500h+var_4E0], ecx
0x1800321ca  cmp     ecx, r13d
0x1800321cd  jbe     short loc_18003221D
0x1800321cf  mov     rcx, cs:ghTapisrvHeap; hHeap
0x1800321d6  add     r13d, 200h
0x1800321dd  mov     r8d, r13d; dwBytes
0x1800321e0  mov     edx, 8; dwFlags
0x1800321e5  call    cs:__imp_HeapAlloc
0x1800321eb  mov     r12, rax
0x1800321ee  test    rax, rax
0x1800321f1  jz      loc_18003228E
0x1800321f7  test    esi, esi
0x1800321f9  jz      short loc_180032211
0x1800321fb  mov     r8d, esi; Size
0x1800321fe  mov     rdx, rbx; Src
0x180032201  mov     rcx, rax; void *
0x180032204  call    memcpy_0
0x180032209  mov     rcx, rbx; lpMem
0x18003220c  call    ServerFree
0x180032211  mov     eax, [rsp+500h+var_4DC]
0x180032215  mov     rbx, r12
0x180032218  mov     r12d, [rsp+500h+var_4D8]
0x18003221d  mov     ecx, esi
0x18003221f  lea     rdx, [rsp+500h+FindFileData.cFileName]; Src
0x180032224  add     rcx, rbx; void *
0x180032227  mov     r8d, eax; Size
0x18003222a  call    memcpy_0
0x18003222f  mov     esi, [rsp+500h+var_4E0]
0x180032233  lea     rdx, [rsp+500h+FindFileData]; lpFindFileData
0x180032238  inc     r12d
0x18003223b  mov     rcx, r15; hFindFile
0x18003223e  mov     [rsp+500h+var_4D8], r12d
0x180032243  call    cs:__imp_FindNextFileW
0x180032249  test    eax, eax
0x18003224b  jnz     loc_18003218E
0x180032251  mov     rcx, r15; hFindFile
0x180032254  call    cs:__imp_FindClose
0x18003225a  xor     ecx, ecx; BindingHandle
0x18003225c  call    cs:__imp_RpcImpersonateClient
0x180032262  test    eax, eax
0x180032264  jz      short loc_1800322A3
0x180032266  mov     r8d, eax
0x180032269  lea     rdx, aMgetavailablep_0; "MGetAvailableProviders: RpcImpersonateC"...
0x180032270  mov     ecx, 10002h
0x180032275  call    TRACELogPrint
0x18003227a  mov     rcx, rbx; lpMem
0x18003227d  mov     dword ptr [r14], 80000048h
0x180032284  call    ServerFree
0x180032289  jmp     loc_1800324DA
0x18003228e  mov     rcx, r15; hFindFile
0x180032291  call    cs:__imp_FindClose
0x180032297  mov     dword ptr [r14], 80000044h
0x18003229e  jmp     loc_1800324DA
0x1800322a3  lea     rdx, [rsp+500h+lpMem]
0x1800322a8  mov     rcx, rbx; lpString
0x1800322ab  call    GetProviderFriendlyName
0x1800322b0  mov     r15d, eax
0x1800322b3  call    cs:__imp_RpcRevertToSelf
0x1800322b9  xor     r8d, r8d
0x1800322bc  test    r15d, r15d
0x1800322bf  jnz     short loc_1800322CE
0x1800322c1  mov     rdx, rbx
0x1800322c4  mov     [rsp+500h+lpMem], rbx
0x1800322c9  mov     r15d, esi
0x1800322cc  jmp     short loc_1800322D8
0x1800322ce  mov     rdx, [rsp+500h+lpMem]
0x1800322d3  mov     [rsp+500h+lpMem], rdx
0x1800322d8  mov     eax, [rdi+4]
0x1800322db  lea     ecx, [r12+r12*4]
0x1800322df  shl     ecx, 2
0x1800322e2  add     eax, ecx
0x1800322e4  mov     [rsp+500h+var_4C8], rcx
0x1800322e9  add     eax, r15d
0x1800322ec  add     eax, esi
0x1800322ee  mov     [rdi+4], eax
0x1800322f1  cmp     eax, [rdi]
0x1800322f3  ja      loc_1800324B0
0x1800322f9  add     [rdi+8], ecx
0x1800322fc  lea     r15, [rdi+18h]
0x180032300  mov     r12, rbx
0x180032303  mov     [rsp+500h+var_4E0], r8d
0x180032308  mov     r13, rdx
0x18003230b  mov     esi, r8d
0x18003230e  mov     eax, r8d
0x180032311  mov     [rsp+500h+var_4DC], eax
0x180032315  cmp     eax, [rsp+500h+var_4D8]
0x180032319  jnb     loc_18003249E
0x18003231f  test    r12, r12
0x180032322  jz      loc_18003248A
0x180032328  test    r13, r13
0x18003232b  jz      loc_18003248A
0x180032331  mov     rcx, r12; lpLibFileName
0x180032334  call    cs:__imp_LoadLibraryW
0x18003233a  xor     r8d, r8d
0x18003233d  mov     rsi, rax
0x180032340  test    rax, rax
0x180032343  jnz     short loc_18003237E
0x180032345  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180032349  mov     rax, rcx
0x18003234c  inc     rax
0x18003234f  cmp     [r12+rax*2], r8w
0x180032354  jnz     short loc_18003234C
0x180032356  lea     r12, [r12+rax*2]
0x18003235a  mov     rax, rcx
0x18003235d  add     r12, 2
0x180032361  inc     rax
0x180032364  cmp     [r13+rax*2+0], r8w
0x18003236a  jnz     short loc_180032361
0x18003236c  mov     esi, [rsp+500h+var_4E0]
0x180032370  lea     r13, [r13+rax*2+0]
0x180032375  add     r13, 2
0x180032379  jmp     loc_18003247F
0x18003237e  lea     rdx, aTspiProviderin; "TSPI_providerInstall"
0x180032385  mov     rcx, rsi; hModule
0x180032388  call    cs:__imp_GetProcAddress
0x18003238e  xor     edx, edx
0x180032390  mov     ecx, edx
0x180032392  test    rax, rax
0x180032395  lea     rdx, aTspiProviderco; "TSPI_providerConfig"
0x18003239c  setnz   cl
0x18003239f  mov     [r15+10h], ecx
0x1800323a3  mov     rcx, rsi; hModule
0x1800323a6  call    cs:__imp_GetProcAddress
0x1800323ac  test    rax, rax
0x1800323af  jnz     short loc_1800323C6
0x1800323b1  lea     rdx, aTuispiProvider; "TUISPI_providerConfig"
0x1800323b8  mov     rcx, rsi; hModule
0x1800323bb  call    cs:__imp_GetProcAddress
0x1800323c1  test    rax, rax
0x1800323c4  jz      short loc_1800323CB
0x1800323c6  or      dword ptr [r15+10h], 2
0x1800323cb  lea     rdx, aTspiProviderre; "TSPI_providerRemove"
0x1800323d2  mov     rcx, rsi; hModule
0x1800323d5  call    cs:__imp_GetProcAddress
0x1800323db  test    rax, rax
0x1800323de  jz      short loc_1800323E5
0x1800323e0  or      dword ptr [r15+10h], 4
0x1800323e5  mov     rcx, rsi; hLibModule
0x1800323e8  call    cs:__imp_FreeLibrary
0x1800323ee  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800323f2  xor     esi, esi
0x1800323f4  inc     rcx
0x1800323f7  cmp     [r12+rcx*2], si
0x1800323fc  jnz     short loc_1800323F4
0x1800323fe  lea     ecx, ds:2[rcx*2]
0x180032405  mov     rdx, r12; Src
0x180032408  mov     [r15], ecx
0x18003240b  mov     eax, [rdi+8]
0x18003240e  mov     r8d, ecx; Size
0x180032411  mov     [r15+4], eax
0x180032415  lea     rcx, [rdi+rax]; void *
0x180032419  call    memcpy_0
0x18003241e  mov     eax, [r15]
0x180032421  add     [rdi+8], eax
0x180032424  mov     eax, [r15]
0x180032427  shr     rax, 1
0x18003242a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003242e  lea     r12, [r12+rax*2]
0x180032432  inc     rcx
0x180032435  cmp     [r13+rcx*2+0], si
0x18003243b  jnz     short loc_180032432
0x18003243d  lea     ecx, ds:2[rcx*2]
0x180032444  mov     rdx, r13; Src
0x180032447  mov     [r15+8], ecx
0x18003244b  mov     eax, [rdi+8]
0x18003244e  mov     r8d, ecx; Size
0x180032451  mov     [r15+0Ch], eax
0x180032455  lea     rcx, [rdi+rax]; void *
0x180032459  call    memcpy_0
0x18003245e  mov     eax, [r15+8]
0x180032462  add     [rdi+8], eax
0x180032465  mov     eax, [r15+8]
0x180032469  mov     esi, [rsp+500h+var_4E0]
0x18003246d  shr     rax, 1
0x180032470  inc     esi
0x180032472  mov     [rsp+500h+var_4E0], esi
0x180032476  add     r15, 14h
0x18003247a  lea     r13, [r13+rax*2+0]
0x18003247f  mov     eax, [rsp+500h+var_4DC]
0x180032483  inc     eax
0x180032485  jmp     loc_180032311
0x18003248a  mov     r8d, eax
0x18003248d  lea     rdx, aFileNameOrFrie; "file name or friendly name empty for %d"...
0x180032494  mov     ecx, 10002h
0x180032499  call    TRACELogPrint
0x18003249e  mov     rax, [rsp+500h+var_4C8]
0x1800324a3  mov     [rdi+10h], eax
0x1800324a6  mov     [rdi+0Ch], esi
0x1800324a9  mov     dword ptr [rdi+14h], 18h
0x1800324b0  mov     rcx, rbx; lpMem
0x1800324b3  call    ServerFree
0x1800324b8  mov     rcx, [rsp+500h+lpMem]; lpMem
0x1800324bd  cmp     rcx, rbx
0x1800324c0  jz      short loc_1800324C7
0x1800324c2  call    ServerFree
0x1800324c7  xor     r12d, r12d
0x1800324ca  mov     eax, [rdi+8]
0x1800324cd  mov     rcx, [rsp+500h+var_4C0]
0x1800324d2  add     eax, 3Ch ; '<'
0x1800324d5  mov     [rcx], eax
0x1800324d7  mov     [r14], r12d
0x1800324da  mov     rcx, [rbp+400h+var_40]
0x1800324e1  xor     rcx, rsp; StackCookie
0x1800324e4  call    __security_check_cookie
0x1800324e9  mov     rbx, [rsp+500h+arg_0]
0x1800324f1  add     rsp, 4D0h
0x1800324f8  pop     r15
0x1800324fa  pop     r14
0x1800324fc  pop     r13
0x1800324fe  pop     r12
0x180032500  pop     rdi
0x180032501  pop     rsi
0x180032502  pop     rbp
0x180032503  retn
```
