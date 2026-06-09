# WLUIGetProfileKey(void *,ushort const *,_GUID *,ulong *,ushort * *)

- ea: `0x180006588`
- end: `0x180006752`
- name: `?WLUIGetProfileKey@@YAKPEAXPEBGPEAU_GUID@@PEAKPEAPEAG@Z`
- size: `458`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, struct _GUID *, unsigned int *pdwFlags, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000d464`
- `0x180011680`

## callees

- `0x180006588`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18000667e`
- `KERNEL32!MultiByteToWideChar` at `0x18000667e`
- `wlanapi!WpFreeProfile` at `0x180006741`
- `wlanapi!WpFreeProfile` at `0x180006741`
- `wlanapi!WlanGetProfile` at `0x1800065ce`
- `wlanapi!WlanGetProfile` at `0x1800065ce`
- `wlanapi!WlanAllocateMemory` at `0x180006656`
- `wlanapi!WlanAllocateMemory` at `0x1800066a7`
- `wlanapi!WlanAllocateMemory` at `0x180006656`
- `wlanapi!WlanAllocateMemory` at `0x1800066a7`
- `wlanapi!WlanFreeMemory` at `0x18000668b`
- `wlanapi!WlanFreeMemory` at `0x18000672f`
- `wlanapi!WlanFreeMemory` at `0x18000668b`
- `wlanapi!WlanFreeMemory` at `0x18000672f`
- `wlanapi!WpParseProfileXml` at `0x1800065ec`
- `wlanapi!WpParseProfileXml` at `0x1800065ec`

## pseudocode

```c
__int64 __fastcall WLUIGetProfileKey(
        void *a1,
        const unsigned __int16 *a2,
        struct _GUID *a3,
        unsigned int *pdwFlags,
        unsigned __int16 **a5)
{
  DWORD Profile; // esi
  __int64 v6; // rdx
  __int64 v7; // rdi
  int v8; // ecx
  WCHAR *Memory; // rax
  PVOID v10; // rbx
  unsigned int v11; // eax
  __int64 v12; // r11
  __int64 v13; // r10
  __int64 i; // r9
  __int64 v15; // r9
  __int16 v16; // cx
  DWORD pdwGrantedAccess; // [rsp+40h] [rbp-28h] BYREF
  __int64 v19; // [rsp+48h] [rbp-20h] BYREF
  LPWSTR pstrProfileXml; // [rsp+50h] [rbp-18h] BYREF

  pstrProfileXml = 0;
  pdwGrantedAccess = 0;
  v19 = 0;
  Profile = WlanGetProfile(a1, a3, a2, 0, &pstrProfileXml, pdwFlags, &pdwGrantedAccess);
  if ( Profile )
    goto LABEL_18;
  Profile = WpParseProfileXml(pstrProfileXml, &v19, 0, 0);
  if ( Profile )
    goto LABEL_18;
  v6 = v19;
  if ( v19 )
  {
    if ( *(_DWORD *)(v19 + 536) == 5304833 )
    {
      v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v19 + 552) + 32LL) + 424LL);
      v8 = *(_DWORD *)(v7 + 64);
      if ( v8 )
      {
        if ( *(_QWORD *)(v7 + 72) && (*(_BYTE *)v7 & 1) == 0 )
        {
          if ( (*(_BYTE *)v7 & 2) != 0 )
          {
            Memory = (WCHAR *)WlanAllocateMemory(2 * v8 + 2);
            v10 = Memory;
            if ( !Memory )
            {
LABEL_18:
              v6 = v19;
              goto LABEL_19;
            }
            v11 = MultiByteToWideChar(0, 0, *(LPCCH *)(v7 + 72), *(_DWORD *)(v7 + 64), Memory, *(_DWORD *)(v7 + 64));
            if ( !v11 )
            {
              WlanFreeMemory(v10);
              goto LABEL_18;
            }
            *((_WORD *)v10 + v11) = 0;
          }
          else
          {
            v10 = WlanAllocateMemory(4 * v8 + 2);
            if ( !v10 )
              goto LABEL_18;
            v12 = *(_QWORD *)(v7 + 72);
            v13 = 0;
            for ( i = 0; (unsigned int)v13 < *(_DWORD *)(v7 + 64); i = (unsigned int)(v15 + 1) )
            {
              *((_WORD *)v10 + i) = (*(_BYTE *)(v13 + v12) >> 4)
                                  + 55
                                  + ((unsigned __int8)(*(_BYTE *)(v13 + v12) >> 4) < 0xAu ? 0xFFF9 : 0);
              v15 = (unsigned int)(i + 1);
              v16 = *(_BYTE *)(v13 + v12) & 0xF;
              v13 = (unsigned int)(v13 + 1);
              *((_WORD *)v10 + v15) = v16 + ((unsigned __int8)v16 < 0xAu ? 48 : 55);
            }
            *((_WORD *)v10 + i) = 0;
          }
          *a5 = (unsigned __int16 *)v10;
          goto LABEL_18;
        }
      }
    }
  }
LABEL_19:
  if ( pstrProfileXml )
  {
    WlanFreeMemory(pstrProfileXml);
    v6 = v19;
  }
  if ( v6 )
    WpFreeProfile(v6);
  return Profile;
}

```

## disassembly

```asm
0x180006588  push    rbp
0x18000658a  push    rbx
0x18000658b  push    rsi
0x18000658c  push    rdi
0x18000658d  mov     rbp, rsp
0x180006590  sub     rsp, 68h
0x180006594  mov     rax, r8
0x180006597  mov     [rbp+var_18], 0
0x18000659f  lea     r8, [rbp+var_28]
0x1800065a3  mov     [rbp+var_28], 0
0x1800065aa  mov     [rsp+68h+pdwGrantedAccess], r8; pdwGrantedAccess
0x1800065af  lea     r8, [rbp+var_18]
0x1800065b3  mov     [rsp+68h+pdwFlags], r9; pdwFlags
0x1800065b8  xor     r9d, r9d; pReserved
0x1800065bb  mov     [rsp+68h+pstrProfileXml], r8; pstrProfileXml
0x1800065c0  mov     r8, rdx; strProfileName
0x1800065c3  mov     rdx, rax; pInterfaceGuid
0x1800065c6  mov     [rbp+var_20], 0
0x1800065ce  call    cs:__imp_WlanGetProfile
0x1800065d4  mov     esi, eax
0x1800065d6  test    eax, eax
0x1800065d8  jnz     loc_180006722
0x1800065de  mov     rcx, [rbp+var_18]
0x1800065e2  lea     rdx, [rbp+var_20]
0x1800065e6  xor     r9d, r9d
0x1800065e9  xor     r8d, r8d
0x1800065ec  call    cs:__imp_WpParseProfileXml
0x1800065f2  mov     esi, eax
0x1800065f4  test    eax, eax
0x1800065f6  jnz     loc_180006722
0x1800065fc  mov     rdx, [rbp+var_20]
0x180006600  test    rdx, rdx
0x180006603  jz      loc_180006726
0x180006609  cmp     dword ptr [rdx+218h], 50F201h
0x180006613  jnz     loc_180006726
0x180006619  mov     rax, [rdx+228h]
0x180006620  mov     rcx, [rax+20h]
0x180006624  mov     rdi, [rcx+1A8h]
0x18000662b  mov     ecx, [rdi+40h]
0x18000662e  test    ecx, ecx
0x180006630  jz      loc_180006726
0x180006636  cmp     qword ptr [rdi+48h], 0
0x18000663b  jz      loc_180006726
0x180006641  test    byte ptr [rdi], 1
0x180006644  jnz     loc_180006726
0x18000664a  test    byte ptr [rdi], 2
0x18000664d  jz      short loc_1800066A0
0x18000664f  lea     ecx, ds:2[rcx*2]; dwMemorySize
0x180006656  call    cs:__imp_WlanAllocateMemory
0x18000665c  mov     rbx, rax
0x18000665f  test    rax, rax
0x180006662  jz      loc_180006722
0x180006668  mov     r9d, [rdi+40h]; cbMultiByte
0x18000666c  xor     edx, edx; dwFlags
0x18000666e  mov     r8, [rdi+48h]; lpMultiByteStr
0x180006672  xor     ecx, ecx; CodePage
0x180006674  mov     dword ptr [rsp+68h+pdwFlags], r9d; cchWideChar
0x180006679  mov     [rsp+68h+pstrProfileXml], rax; lpWideCharStr
0x18000667e  call    cs:__imp_MultiByteToWideChar
0x180006684  test    eax, eax
0x180006686  jnz     short loc_180006696
0x180006688  mov     rcx, rbx; pMemory
0x18000668b  call    cs:__imp_WlanFreeMemory
0x180006691  jmp     loc_180006722
0x180006696  mov     ecx, eax
0x180006698  xor     eax, eax
0x18000669a  mov     [rbx+rcx*2], ax
0x18000669e  jmp     short loc_18000671B
0x1800066a0  lea     ecx, ds:2[rcx*4]; dwMemorySize
0x1800066a7  call    cs:__imp_WlanAllocateMemory
0x1800066ad  mov     rbx, rax
0x1800066b0  test    rax, rax
0x1800066b3  jz      short loc_180006722
0x1800066b5  mov     r11, [rdi+48h]
0x1800066b9  xor     r10d, r10d
0x1800066bc  xor     r9d, r9d
0x1800066bf  cmp     [rdi+40h], r9d
0x1800066c3  jbe     short loc_180006714
0x1800066c5  mov     al, [r10+r11]
0x1800066c9  shr     al, 4
0x1800066cc  movzx   ecx, al
0x1800066cf  cmp     cl, 0Ah
0x1800066d2  sbb     dx, dx
0x1800066d5  add     cx, 37h ; '7'
0x1800066d9  and     dx, 0FFF9h
0x1800066de  add     dx, cx
0x1800066e1  mov     [rbx+r9*2], dx
0x1800066e6  inc     r9d
0x1800066e9  mov     al, [r10+r11]
0x1800066ed  and     al, 0Fh
0x1800066ef  movzx   ecx, al
0x1800066f2  cmp     cl, 0Ah
0x1800066f5  sbb     ax, ax
0x1800066f8  inc     r10d
0x1800066fb  and     ax, 0FFF9h
0x1800066ff  add     ax, 37h ; '7'
0x180006703  add     ax, cx
0x180006706  mov     [rbx+r9*2], ax
0x18000670b  inc     r9d
0x18000670e  cmp     r10d, [rdi+40h]
0x180006712  jb      short loc_1800066C5
0x180006714  xor     eax, eax
0x180006716  mov     [rbx+r9*2], ax
0x18000671b  mov     rax, [rbp+arg_20]
0x18000671f  mov     [rax], rbx
0x180006722  mov     rdx, [rbp+var_20]
0x180006726  mov     rcx, [rbp+var_18]; pMemory
0x18000672a  test    rcx, rcx
0x18000672d  jz      short loc_180006739
0x18000672f  call    cs:__imp_WlanFreeMemory
0x180006735  mov     rdx, [rbp+var_20]
0x180006739  test    rdx, rdx
0x18000673c  jz      short loc_180006747
0x18000673e  mov     rcx, rdx
0x180006741  call    cs:__imp_WpFreeProfile
0x180006747  mov     eax, esi
0x180006749  add     rsp, 68h
0x18000674d  pop     rdi
0x18000674e  pop     rsi
0x18000674f  pop     rbx
0x180006750  pop     rbp
0x180006751  retn
```
