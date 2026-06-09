# GetSubCAOverrides

- ea: `0x1800118a4`
- end: `0x180011b0f`
- name: `GetSubCAOverrides`
- size: `619`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180012e10`

## callees

- `0x180005f64`
- `0x18000a6d0`
- `0x18000bd6c`
- `0x18001005c`
- `0x1800118a4`
- `0x180013f28`
- `0x180042630`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011ae2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011ae2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001191d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001191d`

## string_xrefs

- `0x18001190f`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test\SubCAOverrides`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetSubCAOverrides(_DWORD *a1, _QWORD *a2)
{
  LSTATUS v3; // edi
  __int64 v4; // rsi
  char IsEnabled; // al
  unsigned __int64 v6; // rcx
  _DWORD *v7; // rbx
  int *v8; // rdi
  __int64 v9; // rbp
  __int64 v10; // r15
  __int64 v11; // r14
  unsigned int *v12; // r13
  int *v13; // rdi
  __int64 v14; // r14
  char *v15; // r12
  __int64 v16; // r14
  char *v17; // r12
  _DWORD *v18; // rax
  HKEY hKey; // [rsp+48h] [rbp-50h] BYREF

  *a1 = 0;
  *a2 = 0;
  if ( !(unsigned int)__AreTestKeysAllowed(1) )
    return 2149847039LL;
  hKey = 0;
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test\\SubCAOverrides",
         0,
         0x20019u,
         &hKey);
  if ( v3 >= 0 )
  {
    v4 = 0;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl'::`2'::impl);
    v6 = 28;
    if ( !IsEnabled )
      v6 = 10;
    v7 = SafeSusAllocArray(v6, 0x18u);
    if ( v7 )
    {
      v8 = dword_180062840;
      v9 = 2;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl'::`2'::impl) )
      {
        v10 = 2;
        do
        {
          v11 = 5;
          do
          {
            v12 = &v7[6 * v4];
            if ( (int)RegQueryBinaryValue(hKey, *((LPCWSTR *)v8 + 1), (unsigned __int8 **)&v7[6 * v4 + 4], v12 + 2) >= 0
              && v12[2]
              && *(_QWORD *)&v7[6 * v4 + 4] )
            {
              v7[6 * v4] = *v8;
              v7[6 * v4 + 1] = v8[1];
              v4 = (unsigned int)(v4 + 1);
            }
            v8 += 12;
            --v11;
          }
          while ( v11 );
          --v10;
        }
        while ( v10 );
        v13 = dword_1800624D0;
        do
        {
          v14 = 9;
          do
          {
            v15 = (char *)&v7[6 * v4];
            if ( (int)RegQueryBinaryValue(
                        hKey,
                        *((LPCWSTR *)v13 + 1),
                        (unsigned __int8 **)v15 + 2,
                        (unsigned int *)v15 + 2) >= 0
              && *((_DWORD *)v15 + 2)
              && *((_QWORD *)v15 + 2) )
            {
              v7[6 * v4] = *v13;
              v7[6 * v4 + 1] = v13[1];
              v4 = (unsigned int)(v4 + 1);
            }
            v13 += 12;
            --v14;
          }
          while ( v14 );
          --v9;
        }
        while ( v9 );
      }
      else
      {
        do
        {
          v16 = 5;
          do
          {
            v17 = (char *)&v7[6 * v4];
            if ( (int)RegQueryBinaryValue(
                        hKey,
                        *((LPCWSTR *)v8 + 1),
                        (unsigned __int8 **)v17 + 2,
                        (unsigned int *)v17 + 2) >= 0
              && *((_DWORD *)v17 + 2)
              && *((_QWORD *)v17 + 2) )
            {
              v7[6 * v4] = *v8;
              v7[6 * v4 + 1] = v8[1];
              v4 = (unsigned int)(v4 + 1);
            }
            v8 += 12;
            --v16;
          }
          while ( v16 );
          --v9;
        }
        while ( v9 );
      }
      if ( (_DWORD)v4 )
      {
        *a1 = v4;
        v18 = v7;
        v7 = 0;
        *a2 = v18;
        v3 = 0;
      }
      else
      {
        v3 = -2147024637;
      }
    }
    else
    {
      v3 = -2147024882;
    }
    if ( v7 )
      CSusBaseAllocTag<942762101>::operator delete(v7);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800118a4  mov     [rsp+arg_10], rbx
0x1800118a9  push    rbp
0x1800118aa  push    rsi
0x1800118ab  push    rdi
0x1800118ac  push    r12
0x1800118ae  push    r13
0x1800118b0  push    r14
0x1800118b2  push    r15
0x1800118b4  sub     rsp, 60h
0x1800118b8  mov     rax, cs:__security_cookie
0x1800118bf  xor     rax, rsp
0x1800118c2  mov     [rsp+98h+var_48], rax
0x1800118c7  mov     [rsp+98h+var_58], rdx
0x1800118cc  mov     [rsp+98h+var_60], rcx
0x1800118d1  mov     dword ptr [rcx], 0
0x1800118d7  mov     qword ptr [rdx], 0
0x1800118de  mov     cl, 1; bool
0x1800118e0  call    ?__AreTestKeysAllowed@@YAH_N@Z; __AreTestKeysAllowed(bool)
0x1800118e5  test    eax, eax
0x1800118e7  jnz     short loc_1800118F3
0x1800118e9  mov     eax, 80240FFFh
0x1800118ee  jmp     loc_180011AEA
0x1800118f3  mov     [rsp+98h+hKey], 0
0x1800118fc  lea     rax, [rsp+98h+hKey]
0x180011901  mov     [rsp+98h+phkResult], rax; phkResult
0x180011906  mov     r9d, 20019h; samDesired
0x18001190c  xor     r8d, r8d; ulOptions
0x18001190f  lea     rdx, ?c_szSubCAOverridesTestKey@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180011916  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001191d  call    cs:__imp_RegOpenKeyExW
0x180011923  mov     edi, eax
0x180011925  test    eax, eax
0x180011927  js      loc_180011AD8
0x18001192d  xor     esi, esi
0x18001192f  mov     [rsp+98h+var_68], rsi
0x180011934  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl(void)'::`2'::impl
0x18001193b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(void)
0x180011940  lea     edx, [rsi+18h]; unsigned __int64
0x180011943  test    al, al
0x180011945  lea     ecx, [rsi+1Ch]
0x180011948  jnz     short loc_18001194D
0x18001194a  lea     ecx, [rsi+0Ah]; unsigned __int64
0x18001194d  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x180011952  mov     [rsp+98h+var_68], rax
0x180011957  mov     rbx, rax
0x18001195a  test    rax, rax
0x18001195d  jnz     short loc_180011969
0x18001195f  mov     edi, 8007000Eh
0x180011964  jmp     loc_180011ACA
0x180011969  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::GetImpl(void)'::`2'::impl
0x180011970  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UpdateWUTrustAnchor_58093369>::__private_IsEnabled(void)
0x180011975  lea     rdi, dword_180062840
0x18001197c  mov     ebp, 2
0x180011981  test    al, al
0x180011983  jz      loc_180011A4D
0x180011989  mov     r15d, ebp
0x18001198c  mov     r14d, 5
0x180011992  lea     r12, [rsi+rsi*2]
0x180011996  lea     r13, [rbx+r12*8]
0x18001199a  lea     r8, [r12+2]
0x18001199f  lea     r8, [rbx+r8*8]; unsigned __int8 **
0x1800119a3  lea     r9, [r13+8]; unsigned int *
0x1800119a7  mov     rdx, [rdi+8]; lpValueName
0x1800119ab  mov     rcx, [rsp+98h+hKey]; hKey
0x1800119b0  call    ?RegQueryBinaryValue@@YAJPEAUHKEY__@@PEB_WPEAPEAEPEAK@Z; RegQueryBinaryValue(HKEY__ *,wchar_t const *,uchar * *,ulong *)
0x1800119b5  test    eax, eax
0x1800119b7  js      short loc_1800119D8
0x1800119b9  cmp     dword ptr [r13+8], 0
0x1800119be  jbe     short loc_1800119D8
0x1800119c0  cmp     qword ptr [rbx+r12*8+10h], 0
0x1800119c6  jz      short loc_1800119D8
0x1800119c8  mov     eax, [rdi]
0x1800119ca  mov     [rbx+r12*8], eax
0x1800119ce  mov     eax, [rdi+4]
0x1800119d1  mov     [rbx+r12*8+4], eax
0x1800119d6  inc     esi
0x1800119d8  add     rdi, 30h ; '0'
0x1800119dc  sub     r14, 1
0x1800119e0  jnz     short loc_180011992
0x1800119e2  sub     r15, 1
0x1800119e6  jnz     short loc_18001198C
0x1800119e8  lea     rdi, dword_1800624D0
0x1800119ef  mov     r14d, 9
0x1800119f5  lea     r15, [rsi+rsi*2]
0x1800119f9  lea     r12, [rbx+r15*8]
0x1800119fd  lea     r13, [rbx+r15*8]
0x180011a01  lea     r9, [r12+8]; unsigned int *
0x180011a06  lea     r8, [r13+10h]; unsigned __int8 **
0x180011a0a  mov     rdx, [rdi+8]; lpValueName
0x180011a0e  mov     rcx, [rsp+98h+hKey]; hKey
0x180011a13  call    ?RegQueryBinaryValue@@YAJPEAUHKEY__@@PEB_WPEAPEAEPEAK@Z; RegQueryBinaryValue(HKEY__ *,wchar_t const *,uchar * *,ulong *)
0x180011a18  test    eax, eax
0x180011a1a  js      short loc_180011A3B
0x180011a1c  cmp     dword ptr [r12+8], 0
0x180011a22  jbe     short loc_180011A3B
0x180011a24  cmp     qword ptr [r13+10h], 0
0x180011a29  jz      short loc_180011A3B
0x180011a2b  mov     eax, [rdi]
0x180011a2d  mov     [rbx+r15*8], eax
0x180011a31  mov     eax, [rdi+4]
0x180011a34  mov     [rbx+r15*8+4], eax
0x180011a39  inc     esi
0x180011a3b  add     rdi, 30h ; '0'
0x180011a3f  sub     r14, 1
0x180011a43  jnz     short loc_1800119F5
0x180011a45  sub     rbp, 1
0x180011a49  jnz     short loc_1800119EF
0x180011a4b  jmp     short loc_180011AA9
0x180011a4d  mov     r14d, 5
0x180011a53  lea     r15, [rsi+rsi*2]
0x180011a57  lea     r12, [rbx+r15*8]
0x180011a5b  lea     r13, [rbx+r15*8]
0x180011a5f  lea     r9, [r12+8]; unsigned int *
0x180011a64  lea     r8, [r13+10h]; unsigned __int8 **
0x180011a68  mov     rdx, [rdi+8]; lpValueName
0x180011a6c  mov     rcx, [rsp+98h+hKey]; hKey
0x180011a71  call    ?RegQueryBinaryValue@@YAJPEAUHKEY__@@PEB_WPEAPEAEPEAK@Z; RegQueryBinaryValue(HKEY__ *,wchar_t const *,uchar * *,ulong *)
0x180011a76  test    eax, eax
0x180011a78  js      short loc_180011A99
0x180011a7a  cmp     dword ptr [r12+8], 0
0x180011a80  jbe     short loc_180011A99
0x180011a82  cmp     qword ptr [r13+10h], 0
0x180011a87  jz      short loc_180011A99
0x180011a89  mov     eax, [rdi]
0x180011a8b  mov     [rbx+r15*8], eax
0x180011a8f  mov     eax, [rdi+4]
0x180011a92  mov     [rbx+r15*8+4], eax
0x180011a97  inc     esi
0x180011a99  add     rdi, 30h ; '0'
0x180011a9d  sub     r14, 1
0x180011aa1  jnz     short loc_180011A53
0x180011aa3  sub     rbp, 1
0x180011aa7  jnz     short loc_180011A4D
0x180011aa9  test    esi, esi
0x180011aab  jz      short loc_180011AC5
0x180011aad  mov     rax, [rsp+98h+var_60]
0x180011ab2  mov     [rax], esi
0x180011ab4  mov     rax, rbx
0x180011ab7  xor     ebx, ebx
0x180011ab9  mov     rcx, [rsp+98h+var_58]
0x180011abe  mov     [rcx], rax
0x180011ac1  xor     edi, edi
0x180011ac3  jmp     short loc_180011ACA
0x180011ac5  mov     edi, 80070103h
0x180011aca  test    rbx, rbx
0x180011acd  jz      short loc_180011AD8
0x180011acf  mov     rcx, rbx; lpMem
0x180011ad2  call    ??3?$CSusBaseAllocTag@$0DIDBGIHF@@@SAXPEAX@Z; CSusBaseAllocTag<942762101>::operator delete(void *)
0x180011ad7  nop
0x180011ad8  mov     rcx, [rsp+98h+hKey]; hKey
0x180011add  test    rcx, rcx
0x180011ae0  jz      short loc_180011AE8
0x180011ae2  call    cs:__imp_RegCloseKey
0x180011ae8  mov     eax, edi
0x180011aea  mov     rcx, [rsp+98h+var_48]
0x180011aef  xor     rcx, rsp; StackCookie
0x180011af2  call    __security_check_cookie
0x180011af7  mov     rbx, [rsp+98h+arg_10]
0x180011aff  add     rsp, 60h
0x180011b03  pop     r15
0x180011b05  pop     r14
0x180011b07  pop     r13
0x180011b09  pop     r12
0x180011b0b  pop     rdi
0x180011b0c  pop     rsi
0x180011b0d  pop     rbp
0x180011b0e  retn
```
