# mciLoadCommandResource

- ea: `0x180012f30`
- end: `0x180013322`
- name: `mciLoadCommandResource`
- size: `1010`
- prototype: `UINT __stdcall(HANDLE hInstance, LPCWSTR lpResName, UINT wType)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800127ac`
- `0x180012f30`
- `0x180013f64`

## callees

- `0x180003a2c`
- `0x18000a264`
- `0x18000b1f8`
- `0x18000b42c`
- `0x18000b6d4`
- `0x18000c990`
- `0x1800126c0`
- `0x180012f30`
- `0x18001a408`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001328c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001328c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800130e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800130e1`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180013149`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x180013149`
- `api-ms-win-core-libraryloader-l1-2-0!FreeResource` at `0x18001327e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeResource` at `0x18001327e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180013134`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180013134`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800130c2`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800130c2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180012fd4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180012fd4`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800130cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800130ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800130cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800130ec`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180013103`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18001311f`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180013103`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18001311f`

## pseudocode

```c
UINT __stdcall mciLoadCommandResource(HANDLE hInstance, LPCWSTR lpResName, UINT wType)
{
  HMODULE Library; // rdi
  HINSTANCE v7; // rcx
  WCHAR *v8; // rcx
  LPCWSTR i; // rdx
  UINT v10; // ebx
  HRSRC ResourceW; // rax
  HGLOBAL Resource; // rax
  void *v13; // rbx
  char *v14; // rax
  char *v15; // r12
  LPCWSTR v16; // rcx
  __int64 v17; // rdx
  unsigned int v18; // esi
  char *j; // r11
  unsigned int v20; // eax
  __int64 v21; // r11
  __int64 v22; // rax
  unsigned int *v23; // r14
  _DWORD *v25; // r11
  signed __int64 v26; // r15
  char *v27; // rsi
  unsigned int v28; // eax
  int v29; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR FilePart; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR FileName[16]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  v29 = 0;
  if ( !MCI_bDeviceListInitialized && !(unsigned int)mciInitDeviceList() )
    return -1;
  Library = 0;
  if ( bCoreTableLoaded )
    goto LABEL_15;
  bCoreTableLoaded = 1;
  if ( (unsigned __int64)lpResName >= 0x10000 )
  {
    if ( !lstrcmpiW(wszCoreTable, lpResName) )
      goto LABEL_15;
    v7 = ghInst;
LABEL_10:
    if ( mciLoadCommandResource(v7, (LPCWSTR)0xC8, 0) == -1
      && WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids);
    }
    goto LABEL_15;
  }
  v7 = ghInst;
  if ( hInstance != ghInst || (_DWORD)lpResName != 200 )
    goto LABEL_10;
LABEL_15:
  if ( (unsigned __int64)lpResName < 0x10000 )
    goto LABEL_24;
  FilePart = 0;
  v8 = FileName;
  for ( i = lpResName; i < lpResName + 8; ++v8 )
  {
    if ( !*i )
      break;
    if ( (unsigned __int64)(v8 - FileName) >= 0xD )
      break;
    *v8 = *i++;
  }
  StringCchCopyW(v8, 13 - (v8 - FileName), wszTypeTableExtension);
  if ( SearchPathW(0, FileName, 0, 0x104u, Buffer, &FilePart)
    && (v10 = SetErrorMode(1u), Library = LoadLibraryExW(Buffer, 0, 1u), SetErrorMode(v10), Library)
    && (ResourceW = FindResourceW(Library, lpResName, (LPCWSTR)0xA)) != 0 )
  {
    hInstance = Library;
  }
  else
  {
LABEL_24:
    ResourceW = FindResourceW((HMODULE)hInstance, lpResName, (LPCWSTR)0xA);
    if ( !ResourceW )
      goto LABEL_52;
  }
  Resource = LoadResource((HMODULE)hInstance, ResourceW);
  v13 = Resource;
  if ( !Resource )
    goto LABEL_52;
  v14 = (char *)LockResource(Resource);
  v15 = v14;
  if ( !v14 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v17 = 22;
      goto LABEL_50;
    }
    goto LABEL_51;
  }
  v18 = 0;
  for ( j = v14; ; j = (char *)(v20 + v21) )
  {
    v20 = mciEatCommandEntry(j, 0, &v29);
    if ( !v29 )
    {
      ++v18;
      continue;
    }
    if ( v29 == 6 )
      break;
  }
  if ( !v18 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v17 = 23;
      goto LABEL_50;
    }
    goto LABEL_51;
  }
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids, v18);
  }
  v22 = winmmAlloc(4 * v18 + 4);
  v23 = (unsigned int *)v22;
  if ( v22 )
  {
    v25 = (_DWORD *)v22;
    v26 = (unsigned __int64)(4 * v18 + 4) >> 1;
    v27 = v15;
    while ( v25 - v23 < v26 )
    {
      v28 = mciEatCommandEntry(v27, 0, &v29);
      if ( v29 )
      {
        if ( v29 == 6 )
        {
          *v25 = -1;
          return mciRegisterCommandTable(v13, v23, wType, Library);
        }
      }
      else
      {
        *v25++ = (_DWORD)v27 - (_DWORD)v15;
      }
      v27 += v28;
    }
    return mciRegisterCommandTable(v13, v23, wType, Library);
  }
  else
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      v17 = 25;
LABEL_50:
      WPP_SF_(*((_QWORD *)v16 + 2), v17, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids);
    }
LABEL_51:
    FreeResource(v13);
LABEL_52:
    if ( Library )
      FreeLibrary(Library);
    return -1;
  }
}

```

## disassembly

```asm
0x180012f30  mov     [rsp-8+arg_10], rbx
0x180012f35  push    rbp
0x180012f36  push    rsi
0x180012f37  push    rdi
0x180012f38  push    r12
0x180012f3a  push    r13
0x180012f3c  push    r14
0x180012f3e  push    r15
0x180012f40  lea     rbp, [rsp-180h]
0x180012f48  sub     rsp, 280h
0x180012f4f  mov     rax, cs:__security_cookie
0x180012f56  xor     rax, rsp
0x180012f59  mov     [rbp+1B0h+var_40], rax
0x180012f60  xor     r15d, r15d
0x180012f63  mov     r13d, r8d
0x180012f66  cmp     cs:MCI_bDeviceListInitialized, r15d
0x180012f6d  mov     rsi, rdx
0x180012f70  mov     r14, rcx
0x180012f73  mov     [rsp+2B0h+var_280], r15d
0x180012f78  jnz     short loc_180012F87
0x180012f7a  call    mciInitDeviceList
0x180012f7f  test    eax, eax
0x180012f81  jz      loc_180013292
0x180012f87  cmp     cs:?bCoreTableLoaded@@3HA, r15d; int bCoreTableLoaded
0x180012f8e  lea     rbx, WPP_GLOBAL_Control
0x180012f95  mov     rdi, r15
0x180012f98  mov     r12d, 1
0x180012f9e  jnz     loc_180013027
0x180012fa4  mov     cs:?bCoreTableLoaded@@3HA, r12d; int bCoreTableLoaded
0x180012fab  cmp     rsi, 10000h
0x180012fb2  jnb     short loc_180012FCA
0x180012fb4  mov     rcx, cs:ghInst
0x180012fbb  cmp     r14, rcx
0x180012fbe  jnz     short loc_180012FE5
0x180012fc0  cmp     esi, 0C8h
0x180012fc6  jnz     short loc_180012FE5
0x180012fc8  jmp     short loc_180013027
0x180012fca  mov     rdx, rsi; lpString2
0x180012fcd  lea     rcx, ?wszCoreTable@@3PAGA; "core"
0x180012fd4  call    cs:__imp_lstrcmpiW
0x180012fda  test    eax, eax
0x180012fdc  jz      short loc_180013027
0x180012fde  mov     rcx, cs:ghInst; hInstance
0x180012fe5  xor     r8d, r8d; wType
0x180012fe8  mov     edx, 0C8h; lpResName
0x180012fed  call    mciLoadCommandResource
0x180012ff2  cmp     eax, 0FFFFFFFFh
0x180012ff5  jnz     short loc_180013027
0x180012ff7  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ffe  cmp     rcx, rbx
0x180013001  jz      short loc_180013027
0x180013003  test    dword ptr [rcx+1Ch], 400000h
0x18001300a  jz      short loc_180013027
0x18001300c  cmp     [rcx+19h], r12b
0x180013010  jb      short loc_180013027
0x180013012  mov     rcx, [rcx+10h]
0x180013016  lea     r8, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids
0x18001301d  mov     edx, 11h
0x180013022  call    WPP_SF_
0x180013027  cmp     rsi, 10000h
0x18001302e  jb      loc_180013113
0x180013034  lea     r9, [rsi+10h]
0x180013038  mov     [rsp+2B0h+FilePart], r15
0x18001303d  lea     rcx, [rsp+2B0h+FileName]
0x180013042  mov     rdx, rsi
0x180013045  mov     r10d, 0Dh
0x18001304b  cmp     rsi, r9
0x18001304e  jnb     short loc_18001307E
0x180013050  movzx   r8d, word ptr [rdx]
0x180013054  test    r8w, r8w
0x180013058  jz      short loc_18001307E
0x18001305a  lea     r11, [rsp+2B0h+FileName]
0x18001305f  mov     rax, rcx
0x180013062  sub     rax, r11
0x180013065  sar     rax, 1
0x180013068  cmp     rax, r10
0x18001306b  jnb     short loc_18001307E
0x18001306d  mov     [rcx], r8w
0x180013071  add     rdx, 2
0x180013075  add     rcx, 2; unsigned __int16 *
0x180013079  cmp     rdx, r9
0x18001307c  jb      short loc_180013050
0x18001307e  lea     rdx, [rsp+2B0h+FileName]
0x180013083  mov     rax, rcx
0x180013086  sub     rax, rdx
0x180013089  lea     r8, ?wszTypeTableExtension@@3PAGA; ".mci"
0x180013090  sar     rax, 1
0x180013093  sub     r10, rax
0x180013096  mov     rdx, r10; unsigned __int64
0x180013099  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001309e  lea     rax, [rsp+2B0h+FilePart]
0x1800130a3  mov     r9d, 104h; nBufferLength
0x1800130a9  mov     [rsp+2B0h+lpFilePart], rax; lpFilePart
0x1800130ae  lea     rdx, [rsp+2B0h+FileName]; lpFileName
0x1800130b3  lea     rax, [rsp+2B0h+Buffer]
0x1800130b8  xor     r8d, r8d; lpExtension
0x1800130bb  xor     ecx, ecx; lpPath
0x1800130bd  mov     [rsp+2B0h+lpBuffer], rax; lpBuffer
0x1800130c2  call    cs:__imp_SearchPathW
0x1800130c8  test    eax, eax
0x1800130ca  jz      short loc_180013113
0x1800130cc  mov     ecx, r12d; uMode
0x1800130cf  call    cs:__imp_SetErrorMode
0x1800130d5  mov     r8d, r12d; dwFlags
0x1800130d8  lea     rcx, [rsp+2B0h+Buffer]; lpLibFileName
0x1800130dd  xor     edx, edx; hFile
0x1800130df  mov     ebx, eax
0x1800130e1  call    cs:__imp_LoadLibraryExW
0x1800130e7  mov     ecx, ebx; uMode
0x1800130e9  mov     rdi, rax
0x1800130ec  call    cs:__imp_SetErrorMode
0x1800130f2  test    rdi, rdi
0x1800130f5  jz      short loc_180013113
0x1800130f7  mov     r8d, 0Ah; lpType
0x1800130fd  mov     rdx, rsi; lpName
0x180013100  mov     rcx, rdi; hModule
0x180013103  call    cs:__imp_FindResourceW
0x180013109  test    rax, rax
0x18001310c  jz      short loc_180013113
0x18001310e  mov     r14, rdi
0x180013111  jmp     short loc_18001312E
0x180013113  mov     r8d, 0Ah; lpType
0x180013119  mov     rdx, rsi; lpName
0x18001311c  mov     rcx, r14; hModule
0x18001311f  call    cs:__imp_FindResourceW
0x180013125  test    rax, rax
0x180013128  jz      loc_180013284
0x18001312e  mov     rdx, rax; hResInfo
0x180013131  mov     rcx, r14; hModule
0x180013134  call    cs:__imp_LoadResource
0x18001313a  mov     rbx, rax
0x18001313d  test    rax, rax
0x180013140  jz      loc_180013284
0x180013146  mov     rcx, rax; hResData
0x180013149  call    cs:__imp_LockResource
0x18001314f  mov     r12, rax
0x180013152  test    rax, rax
0x180013155  jnz     short loc_18001318F
0x180013157  mov     rcx, cs:WPP_GLOBAL_Control
0x18001315e  lea     rax, WPP_GLOBAL_Control
0x180013165  cmp     rcx, rax
0x180013168  jz      loc_18001327B
0x18001316e  test    dword ptr [rcx+1Ch], 400000h
0x180013175  jz      loc_18001327B
0x18001317b  cmp     byte ptr [rcx+19h], 1
0x18001317f  jb      loc_18001327B
0x180013185  lea     edx, [r12+16h]
0x18001318a  jmp     loc_18001326B
0x18001318f  mov     esi, r15d
0x180013192  mov     r11, r12
0x180013195  lea     r8, [rsp+2B0h+var_280]
0x18001319a  xor     edx, edx
0x18001319c  mov     rcx, r11
0x18001319f  call    mciEatCommandEntry
0x1800131a4  mov     ecx, [rsp+2B0h+var_280]
0x1800131a8  test    ecx, ecx
0x1800131aa  jnz     short loc_1800131B0
0x1800131ac  inc     esi
0x1800131ae  jmp     short loc_1800131B5
0x1800131b0  cmp     ecx, 6
0x1800131b3  jz      short loc_1800131BC
0x1800131b5  mov     eax, eax
0x1800131b7  add     r11, rax
0x1800131ba  jmp     short loc_180013195
0x1800131bc  test    esi, esi
0x1800131be  jnz     short loc_1800131F3
0x1800131c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131c7  lea     rax, WPP_GLOBAL_Control
0x1800131ce  cmp     rcx, rax
0x1800131d1  jz      loc_18001327B
0x1800131d7  test    dword ptr [rcx+1Ch], 400000h
0x1800131de  jz      loc_18001327B
0x1800131e4  cmp     byte ptr [rcx+19h], 1
0x1800131e8  jb      loc_18001327B
0x1800131ee  lea     edx, [rsi+17h]
0x1800131f1  jmp     short loc_18001326B
0x1800131f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131fa  lea     rax, WPP_GLOBAL_Control
0x180013201  cmp     rcx, rax
0x180013204  jz      short loc_18001322D
0x180013206  test    dword ptr [rcx+1Ch], 400000h
0x18001320d  jz      short loc_18001322D
0x18001320f  cmp     byte ptr [rcx+19h], 3
0x180013213  jb      short loc_18001322D
0x180013215  mov     rcx, [rcx+10h]
0x180013219  lea     r8, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids
0x180013220  mov     edx, 18h
0x180013225  mov     r9d, esi
0x180013228  call    WPP_SF_d
0x18001322d  lea     r15d, ds:4[rsi*4]
0x180013235  mov     ecx, r15d; Size
0x180013238  call    winmmAlloc
0x18001323d  mov     r14, rax
0x180013240  test    rax, rax
0x180013243  jnz     short loc_180013297
0x180013245  mov     rcx, cs:WPP_GLOBAL_Control
0x18001324c  lea     rax, WPP_GLOBAL_Control
0x180013253  cmp     rcx, rax
0x180013256  jz      short loc_18001327B
0x180013258  test    dword ptr [rcx+1Ch], 400000h
0x18001325f  jz      short loc_18001327B
0x180013261  cmp     byte ptr [rcx+19h], 1
0x180013265  jb      short loc_18001327B
0x180013267  lea     edx, [r14+19h]
0x18001326b  mov     rcx, [rcx+10h]
0x18001326f  lea     r8, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids
0x180013276  call    WPP_SF_
0x18001327b  mov     rcx, rbx; hResData
0x18001327e  call    cs:__imp_FreeResource
0x180013284  test    rdi, rdi
0x180013287  jz      short loc_180013292
0x180013289  mov     rcx, rdi; hLibModule
0x18001328c  call    cs:__imp_FreeLibrary
0x180013292  or      eax, 0FFFFFFFFh
0x180013295  jmp     short loc_1800132F8
0x180013297  mov     r11, r14
0x18001329a  shr     r15, 1
0x18001329d  mov     rsi, r12
0x1800132a0  mov     rax, r11
0x1800132a3  sub     rax, r14
0x1800132a6  sar     rax, 2
0x1800132aa  cmp     rax, r15
0x1800132ad  jge     short loc_1800132E7
0x1800132af  lea     r8, [rsp+2B0h+var_280]
0x1800132b4  xor     edx, edx
0x1800132b6  mov     rcx, rsi
0x1800132b9  call    mciEatCommandEntry
0x1800132be  mov     ecx, [rsp+2B0h+var_280]
0x1800132c2  test    ecx, ecx
0x1800132c4  jnz     short loc_1800132D4
0x1800132c6  mov     ecx, esi
0x1800132c8  sub     ecx, r12d
0x1800132cb  mov     [r11], ecx
0x1800132ce  add     r11, 4
0x1800132d2  jmp     short loc_1800132D9
0x1800132d4  cmp     ecx, 6
0x1800132d7  jz      short loc_1800132E0
0x1800132d9  mov     eax, eax
0x1800132db  add     rsi, rax
0x1800132de  jmp     short loc_1800132A0
0x1800132e0  mov     dword ptr [r11], 0FFFFFFFFh
0x1800132e7  mov     r9, rdi; void *
0x1800132ea  mov     r8d, r13d; unsigned int
0x1800132ed  mov     rdx, r14; unsigned int *
0x1800132f0  mov     rcx, rbx; void *
0x1800132f3  call    ?mciRegisterCommandTable@@YAIPEAXPEAII0@Z; mciRegisterCommandTable(void *,uint *,uint,void *)
0x1800132f8  mov     rcx, [rbp+1B0h+var_40]
0x1800132ff  xor     rcx, rsp; StackCookie
0x180013302  call    __security_check_cookie
0x180013307  mov     rbx, [rsp+2B0h+arg_10]
0x18001330f  add     rsp, 280h
0x180013316  pop     r15
0x180013318  pop     r14
0x18001331a  pop     r13
0x18001331c  pop     r12
0x18001331e  pop     rdi
0x18001331f  pop     rsi
0x180013320  pop     rbp
0x180013321  retn
```
