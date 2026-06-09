# CContactRichPreviewProperty::GetDisplayProperties(CDPA<CContactRichPreviewProperty> *)

- ea: `0x18003b314`
- end: `0x18003b4c8`
- name: `?GetDisplayProperties@CContactRichPreviewProperty@@CAJPEAV?$CDPA@VCContactRichPreviewProperty@@@@@Z`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800399e4`

## callees

- `0x18003afa4`
- `0x18003afcc`
- `0x18003b314`
- `0x18007a950`
- `0x18007ac60`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `SHLWAPI!SHRegEnumUSKeyW` at `0x18003b3cc`
- `SHLWAPI!SHRegEnumUSKeyW` at `0x18003b3cc`
- `SHLWAPI!SHRegCloseUSKey` at `0x18003b3e4`
- `SHLWAPI!SHRegCloseUSKey` at `0x18003b48f`
- `SHLWAPI!SHRegCloseUSKey` at `0x18003b4a8`
- `SHLWAPI!SHRegCloseUSKey` at `0x18003b3e4`
- `SHLWAPI!SHRegCloseUSKey` at `0x18003b48f`
- `SHLWAPI!SHRegCloseUSKey` at `0x18003b4a8`
- `SHLWAPI!SHRegOpenUSKeyW` at `0x18003b395`
- `SHLWAPI!SHRegOpenUSKeyW` at `0x18003b40f`
- `SHLWAPI!SHRegOpenUSKeyW` at `0x18003b395`
- `SHLWAPI!SHRegOpenUSKeyW` at `0x18003b40f`

## string_xrefs

- `0x18003b389`: `Software\Microsoft\WAB\Reading Pane`

## pseudocode

```c
__int64 __fastcall CContactRichPreviewProperty::GetDisplayProperties(__int64 *a1)
{
  CContactRichPreviewProperty *v2; // rbx
  __int64 v3; // rax
  unsigned int v4; // ebx
  DWORD i; // edi
  unsigned int v6; // edx
  int v7; // eax
  HUSKEY hUSKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcchName; // [rsp+38h] [rbp-C8h] BYREF
  struct CContactRichPreviewProperty *v11; // [rsp+40h] [rbp-C0h] BYREF
  HUSKEY phNewUSKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pwzName[80]; // [rsp+50h] [rbp-B0h] BYREF

  phNewUSKey = 0;
  hUSKey = 0;
  memset_0(pwzName, 0, sizeof(pwzName));
  v2 = 0;
  pcchName = 0;
  v11 = 0;
  v3 = OE_DPA_Create(20);
  *a1 = v3;
  if ( v3 )
  {
    if ( SHRegOpenUSKeyW(L"Software\\Microsoft\\WAB\\Reading Pane", 0x20019u, 0, &phNewUSKey, 0) )
    {
      v4 = -2147467259;
    }
    else
    {
      for ( i = 0; ; ++i )
      {
        pcchName = 80;
        if ( SHRegEnumUSKeyW(phNewUSKey, i, pwzName, &pcchName, SHREGENUM_DEFAULT) )
          break;
        if ( hUSKey )
        {
          SHRegCloseUSKey(hUSKey);
          hUSKey = 0;
        }
        if ( !SHRegOpenUSKeyW(pwzName, 0x20019u, phNewUSKey, &hUSKey, 0) )
        {
          if ( v2 )
          {
            CContactRichPreviewProperty::`scalar deleting destructor'(v2, v6);
            v11 = 0;
          }
          v7 = CContactRichPreviewProperty::CreateFromKey(hUSKey, &v11);
          v4 = v7;
          if ( v7 == -2147024809 )
          {
            v2 = v11;
          }
          else
          {
            if ( v7 < 0 )
              goto LABEL_20;
            if ( !v11 )
              break;
            if ( (unsigned int)OE_DPA_InsertPtr(*a1, 0x7FFFFFFF) == -1 )
              goto LABEL_19;
            v2 = 0;
            v11 = 0;
          }
        }
      }
      v4 = 0;
    }
  }
  else
  {
LABEL_19:
    v4 = -2147024882;
  }
LABEL_20:
  if ( hUSKey )
  {
    SHRegCloseUSKey(hUSKey);
    hUSKey = 0;
  }
  if ( phNewUSKey )
    SHRegCloseUSKey(phNewUSKey);
  return v4;
}

```

## disassembly

```asm
0x18003b314  push    rbp
0x18003b316  push    rbx
0x18003b317  push    rsi
0x18003b318  push    rdi
0x18003b319  lea     rbp, [rsp-8]
0x18003b31e  sub     rsp, 108h
0x18003b325  mov     rax, cs:__security_cookie
0x18003b32c  xor     rax, rsp
0x18003b32f  mov     [rbp+20h+var_30], rax
0x18003b333  mov     rsi, rcx
0x18003b336  mov     [rsp+120h+phNewUSKey], 0
0x18003b33f  lea     rcx, [rsp+120h+pwzName]; void *
0x18003b344  mov     [rsp+120h+hUSKey], 0
0x18003b34d  xor     edx, edx; Val
0x18003b34f  mov     r8d, 0A0h; Size
0x18003b355  call    memset_0
0x18003b35a  xor     ebx, ebx
0x18003b35c  mov     [rsp+120h+pcchName], 0
0x18003b364  mov     [rsp+120h+var_E0], rbx
0x18003b369  lea     ecx, [rbx+14h]
0x18003b36c  call    OE_DPA_Create
0x18003b371  mov     [rsi], rax
0x18003b374  test    rax, rax
0x18003b377  jz      loc_18003B480
0x18003b37d  lea     r9, [rsp+120h+phNewUSKey]; phNewUSKey
0x18003b382  mov     [rsp+120h+fIgnoreHKCU], ebx; fIgnoreHKCU
0x18003b386  xor     r8d, r8d; hRelativeUSKey
0x18003b389  lea     rcx, pwzPath; "Software\\Microsoft\\WAB\\Reading Pane"
0x18003b390  mov     edx, 20019h; samDesired
0x18003b395  call    cs:__imp_SHRegOpenUSKeyW
0x18003b39b  test    eax, eax
0x18003b39d  jz      short loc_18003B3A9
0x18003b39f  mov     ebx, 80004005h
0x18003b3a4  jmp     loc_18003B485
0x18003b3a9  xor     edi, edi
0x18003b3ab  mov     rcx, [rsp+120h+phNewUSKey]; hUSKey
0x18003b3b0  lea     r9, [rsp+120h+pcchName]; pcchName
0x18003b3b5  lea     r8, [rsp+120h+pwzName]; pwzName
0x18003b3ba  mov     [rsp+120h+pcchName], 50h ; 'P'
0x18003b3c2  mov     edx, edi; dwIndex
0x18003b3c4  mov     [rsp+120h+fIgnoreHKCU], 0; enumRegFlags
0x18003b3cc  call    cs:__imp_SHRegEnumUSKeyW
0x18003b3d2  test    eax, eax
0x18003b3d4  jnz     loc_18003B47C
0x18003b3da  mov     rcx, [rsp+120h+hUSKey]; hUSKey
0x18003b3df  test    rcx, rcx
0x18003b3e2  jz      short loc_18003B3F3
0x18003b3e4  call    cs:__imp_SHRegCloseUSKey
0x18003b3ea  mov     [rsp+120h+hUSKey], 0
0x18003b3f3  mov     r8, [rsp+120h+phNewUSKey]; hRelativeUSKey
0x18003b3f8  lea     r9, [rsp+120h+hUSKey]; phNewUSKey
0x18003b3fd  mov     edx, 20019h; samDesired
0x18003b402  mov     [rsp+120h+fIgnoreHKCU], 0; fIgnoreHKCU
0x18003b40a  lea     rcx, [rsp+120h+pwzName]; pwzPath
0x18003b40f  call    cs:__imp_SHRegOpenUSKeyW
0x18003b415  test    eax, eax
0x18003b417  jnz     short loc_18003B475
0x18003b419  test    rbx, rbx
0x18003b41c  jz      short loc_18003B42F
0x18003b41e  mov     rcx, rbx; this
0x18003b421  call    ??_GCContactRichPreviewProperty@@AEAAPEAXI@Z; CContactRichPreviewProperty::`scalar deleting destructor'(uint)
0x18003b426  mov     [rsp+120h+var_E0], 0
0x18003b42f  mov     rcx, [rsp+120h+hUSKey]; hRelativeUSKey
0x18003b434  lea     rdx, [rsp+120h+var_E0]; struct CContactRichPreviewProperty **
0x18003b439  call    ?CreateFromKey@CContactRichPreviewProperty@@CAJQEAXPEAPEAV1@@Z; CContactRichPreviewProperty::CreateFromKey(void * const,CContactRichPreviewProperty * *)
0x18003b43e  mov     ebx, eax
0x18003b440  cmp     eax, 80070057h
0x18003b445  jz      short loc_18003B470
0x18003b447  test    eax, eax
0x18003b449  js      short loc_18003B485
0x18003b44b  mov     r8, [rsp+120h+var_E0]
0x18003b450  test    r8, r8
0x18003b453  jz      short loc_18003B47C
0x18003b455  mov     rcx, [rsi]
0x18003b458  mov     edx, 7FFFFFFFh
0x18003b45d  call    OE_DPA_InsertPtr
0x18003b462  cmp     eax, 0FFFFFFFFh
0x18003b465  jz      short loc_18003B480
0x18003b467  xor     ebx, ebx
0x18003b469  mov     [rsp+120h+var_E0], rbx
0x18003b46e  jmp     short loc_18003B475
0x18003b470  mov     rbx, [rsp+120h+var_E0]
0x18003b475  inc     edi
0x18003b477  jmp     loc_18003B3AB
0x18003b47c  xor     ebx, ebx
0x18003b47e  jmp     short loc_18003B485
0x18003b480  mov     ebx, 8007000Eh
0x18003b485  mov     rcx, [rsp+120h+hUSKey]; hUSKey
0x18003b48a  test    rcx, rcx
0x18003b48d  jz      short loc_18003B49E
0x18003b48f  call    cs:__imp_SHRegCloseUSKey
0x18003b495  mov     [rsp+120h+hUSKey], 0
0x18003b49e  mov     rcx, [rsp+120h+phNewUSKey]; hUSKey
0x18003b4a3  test    rcx, rcx
0x18003b4a6  jz      short loc_18003B4AE
0x18003b4a8  call    cs:__imp_SHRegCloseUSKey
0x18003b4ae  mov     eax, ebx
0x18003b4b0  mov     rcx, [rbp+20h+var_30]
0x18003b4b4  xor     rcx, rsp; StackCookie
0x18003b4b7  call    __security_check_cookie
0x18003b4bc  add     rsp, 108h
0x18003b4c3  pop     rdi
0x18003b4c4  pop     rsi
0x18003b4c5  pop     rbx
0x18003b4c6  pop     rbp
0x18003b4c7  retn
```
