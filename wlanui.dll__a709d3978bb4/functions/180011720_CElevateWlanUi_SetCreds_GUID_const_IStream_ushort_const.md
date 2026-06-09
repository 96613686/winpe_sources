# CElevateWlanUi::SetCreds(_GUID const &,IStream *,ushort const *)

- ea: `0x180011720`
- end: `0x18001188a`
- name: `?SetCreds@CElevateWlanUi@@UEAAJAEBU_GUID@@PEAUIStream@@PEBG@Z`
- size: `362`
- prototype: `__int64 __fastcall(CElevateWlanUi *this, const struct _GUID *, struct IStream *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006164`
- `0x18000637c`
- `0x180011720`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180011772`
- `KERNEL32!HeapAlloc` at `0x180011772`
- `KERNEL32!GetProcessHeap` at `0x180011762`
- `KERNEL32!GetProcessHeap` at `0x1800117ee`
- `KERNEL32!GetProcessHeap` at `0x180011838`
- `KERNEL32!GetProcessHeap` at `0x180011854`
- `KERNEL32!GetProcessHeap` at `0x180011762`
- `KERNEL32!GetProcessHeap` at `0x1800117ee`
- `KERNEL32!GetProcessHeap` at `0x180011838`
- `KERNEL32!GetProcessHeap` at `0x180011854`
- `KERNEL32!HeapFree` at `0x1800117fc`
- `KERNEL32!HeapFree` at `0x180011846`
- `KERNEL32!HeapFree` at `0x180011862`
- `KERNEL32!HeapFree` at `0x1800117fc`
- `KERNEL32!HeapFree` at `0x180011846`
- `KERNEL32!HeapFree` at `0x180011862`
- `wlanapi!WlanOpenHandle` at `0x180011756`
- `wlanapi!WlanOpenHandle` at `0x180011756`
- `wlanapi!WlanCloseHandle` at `0x1800117c7`
- `wlanapi!WlanCloseHandle` at `0x1800117c7`

## pseudocode

```c
__int64 __fastcall CElevateWlanUi::SetCreds(
        CElevateWlanUi *this,
        const struct _GUID *a2,
        struct IStream *a3,
        const unsigned __int16 *a4)
{
  int CredsInfoFromStream; // esi
  signed int v8; // ebp
  HANDLE ProcessHeap; // rax
  struct _AUI_CREDS_INFO *v10; // rax
  struct _AUI_CREDS_INFO *v11; // rdi
  void *v12; // rbx
  HANDLE v13; // rax
  _BYTE *v14; // rcx
  __int64 v15; // rdx
  void *v16; // rbx
  HANDLE v17; // rax
  HANDLE v18; // rax
  DWORD v20; // [rsp+20h] [rbp-58h] BYREF
  HANDLE hClientHandle; // [rsp+28h] [rbp-50h] BYREF
  GUID pInterfaceGuid; // [rsp+30h] [rbp-48h] BYREF

  v20 = 0;
  hClientHandle = 0;
  CredsInfoFromStream = 0;
  v8 = WlanOpenHandle(2u, 0, &v20, &hClientHandle);
  if ( v8 )
  {
    v11 = 0;
  }
  else
  {
    ProcessHeap = GetProcessHeap();
    v10 = (struct _AUI_CREDS_INFO *)HeapAlloc(ProcessHeap, 8u, 0x38u);
    v11 = v10;
    if ( v10 )
    {
      CredsInfoFromStream = ReadCredsInfoFromStream(a3, v10);
      if ( CredsInfoFromStream >= 0 )
      {
        pInterfaceGuid = *a2;
        v8 = SaveCreds(hClientHandle, &pInterfaceGuid, a4, v11);
      }
    }
    else
    {
      v8 = 8;
    }
  }
  if ( hClientHandle )
  {
    WlanCloseHandle(hClientHandle, 0);
    hClientHandle = 0;
  }
  if ( v11 )
  {
    if ( *((_DWORD *)v11 + 6) )
    {
      v12 = (void *)*((_QWORD *)v11 + 4);
      if ( v12 )
      {
        v13 = GetProcessHeap();
        HeapFree(v13, 0, v12);
        *((_QWORD *)v11 + 4) = 0;
      }
    }
    if ( *((_DWORD *)v11 + 10) )
    {
      v14 = (_BYTE *)*((_QWORD *)v11 + 6);
      if ( v14 )
      {
        v15 = ((2580 * *((_DWORD *)v11 + 10)) & 0xFFFFFFF0) + 16;
        if ( ((2580 * *((_DWORD *)v11 + 10)) & 0xFFFFFFF0) != 0xFFFFFFF0 )
        {
          do
          {
            *v14++ = 0;
            --v15;
          }
          while ( v15 );
        }
        v16 = (void *)*((_QWORD *)v11 + 6);
        v17 = GetProcessHeap();
        HeapFree(v17, 0, v16);
        *((_QWORD *)v11 + 6) = 0;
      }
    }
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v11);
  }
  if ( v8 )
  {
    if ( v8 > 0 )
      return (unsigned __int16)v8 | 0x80070000;
    else
      return (unsigned int)v8;
  }
  return (unsigned int)CredsInfoFromStream;
}

```

## disassembly

```asm
0x180011720  mov     rax, rsp
0x180011723  push    rbx
0x180011724  push    rbp
0x180011725  push    rsi
0x180011726  push    rdi
0x180011727  push    r14
0x180011729  push    r15
0x18001172b  sub     rsp, 48h
0x18001172f  mov     r14, r9
0x180011732  mov     dword ptr [rax-58h], 0
0x180011739  mov     rbx, r8
0x18001173c  mov     qword ptr [rax-50h], 0
0x180011744  mov     r15, rdx
0x180011747  lea     r9, [rax-50h]; phClientHandle
0x18001174b  xor     esi, esi
0x18001174d  lea     r8, [rax-58h]; pdwNegotiatedVersion
0x180011751  xor     edx, edx; pReserved
0x180011753  lea     ecx, [rsi+2]; dwClientVersion
0x180011756  call    cs:__imp_WlanOpenHandle
0x18001175c  mov     ebp, eax
0x18001175e  test    eax, eax
0x180011760  jnz     short loc_1800117B9
0x180011762  call    cs:__imp_GetProcessHeap
0x180011768  mov     rcx, rax; hHeap
0x18001176b  lea     edx, [rsi+8]; dwFlags
0x18001176e  lea     r8d, [rsi+38h]; dwBytes
0x180011772  call    cs:__imp_HeapAlloc
0x180011778  mov     rdi, rax
0x18001177b  test    rax, rax
0x18001177e  jnz     short loc_180011785
0x180011780  lea     ebp, [rsi+8]
0x180011783  jmp     short loc_1800117BB
0x180011785  mov     rdx, rdi; struct _AUI_CREDS_INFO *
0x180011788  mov     rcx, rbx; pstm
0x18001178b  call    ?ReadCredsInfoFromStream@@YAJPEAUIStream@@PEAU_AUI_CREDS_INFO@@@Z; ReadCredsInfoFromStream(IStream *,_AUI_CREDS_INFO *)
0x180011790  mov     esi, eax
0x180011792  test    eax, eax
0x180011794  js      short loc_1800117BB
0x180011796  movups  xmm0, xmmword ptr [r15]
0x18001179a  mov     rcx, [rsp+78h+hClientHandle]; hClientHandle
0x18001179f  lea     rdx, [rsp+78h+pInterfaceGuid]; pInterfaceGuid
0x1800117a4  mov     r9, rdi; struct _AUI_CREDS_INFO *
0x1800117a7  mov     r8, r14; strProfileName
0x1800117aa  movdqu  xmmword ptr [rsp+78h+pInterfaceGuid.Data1], xmm0
0x1800117b0  call    ?SaveCreds@@YAKPEAXU_GUID@@PEBGPEAU_AUI_CREDS_INFO@@@Z; SaveCreds(void *,_GUID,ushort const *,_AUI_CREDS_INFO *)
0x1800117b5  mov     ebp, eax
0x1800117b7  jmp     short loc_1800117BB
0x1800117b9  xor     edi, edi
0x1800117bb  mov     rcx, [rsp+78h+hClientHandle]; hClientHandle
0x1800117c0  test    rcx, rcx
0x1800117c3  jz      short loc_1800117D6
0x1800117c5  xor     edx, edx; pReserved
0x1800117c7  call    cs:__imp_WlanCloseHandle
0x1800117cd  mov     [rsp+78h+hClientHandle], 0
0x1800117d6  test    rdi, rdi
0x1800117d9  jz      loc_180011868
0x1800117df  cmp     dword ptr [rdi+18h], 0
0x1800117e3  jbe     short loc_18001180A
0x1800117e5  mov     rbx, [rdi+20h]
0x1800117e9  test    rbx, rbx
0x1800117ec  jz      short loc_18001180A
0x1800117ee  call    cs:__imp_GetProcessHeap
0x1800117f4  mov     r8, rbx; lpMem
0x1800117f7  xor     edx, edx; dwFlags
0x1800117f9  mov     rcx, rax; hHeap
0x1800117fc  call    cs:__imp_HeapFree
0x180011802  mov     qword ptr [rdi+20h], 0
0x18001180a  cmp     dword ptr [rdi+28h], 0
0x18001180e  jbe     short loc_180011854
0x180011810  mov     rcx, [rdi+30h]
0x180011814  test    rcx, rcx
0x180011817  jz      short loc_180011854
0x180011819  imul    edx, [rdi+28h], 0A14h
0x180011820  and     edx, 0FFFFFFF0h
0x180011823  add     edx, 10h
0x180011826  jz      short loc_180011834
0x180011828  mov     byte ptr [rcx], 0
0x18001182b  inc     rcx
0x18001182e  sub     rdx, 1
0x180011832  jnz     short loc_180011828
0x180011834  mov     rbx, [rdi+30h]
0x180011838  call    cs:__imp_GetProcessHeap
0x18001183e  mov     r8, rbx; lpMem
0x180011841  xor     edx, edx; dwFlags
0x180011843  mov     rcx, rax; hHeap
0x180011846  call    cs:__imp_HeapFree
0x18001184c  mov     qword ptr [rdi+30h], 0
0x180011854  call    cs:__imp_GetProcessHeap
0x18001185a  mov     r8, rdi; lpMem
0x18001185d  xor     edx, edx; dwFlags
0x18001185f  mov     rcx, rax; hHeap
0x180011862  call    cs:__imp_HeapFree
0x180011868  test    ebp, ebp
0x18001186a  jz      short loc_18001187B
0x18001186c  jg      short loc_180011872
0x18001186e  mov     esi, ebp
0x180011870  jmp     short loc_18001187B
0x180011872  movzx   esi, bp
0x180011875  or      esi, 80070000h
0x18001187b  mov     eax, esi
0x18001187d  add     rsp, 48h
0x180011881  pop     r15
0x180011883  pop     r14
0x180011885  pop     rdi
0x180011886  pop     rsi
0x180011887  pop     rbp
0x180011888  pop     rbx
0x180011889  retn
```
