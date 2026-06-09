# mregHandleInternalMessages

- ea: `0x180007dd0`
- end: `0x1800084bc`
- name: `mregHandleInternalMessages`
- size: `1772`
- prototype: `__int64 __usercall@<rax>(struct _MMDRV *@<rcx>, unsigned __int16 *, unsigned __int64, __int64)`
- caller_count: `7`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800048e0`
- `0x180005030`
- `0x1800078f4`
- `0x180007b00`
- `0x1800095bc`
- `0x18000ffc0`
- `0x1800173c0`

## callees

- `0x180001eb0`
- `0x180004350`
- `0x180007dd0`
- `0x180008be0`
- `0x180009d20`
- `0x180009d64`
- `0x180009d9c`
- `0x18000a4f0`
- `0x18000d630`
- `0x18000da80`
- `0x18000e944`
- `0x18000f1c4`
- `0x18000f1fc`
- `0x1800106c0`
- `0x180015f70`
- `0x180016540`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007f84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008040`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008127`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007f84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008040`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008127`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007e5e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180007e5e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008286`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180008286`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800082cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800082cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800082df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800082df`

## pseudocode

```c
__int64 __fastcall mregHandleInternalMessages(
        struct _MMDRV *a1,
        int a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int16 *a5,
        unsigned __int64 a6,
        int *a7)
{
  __int64 v11; // r14
  int IdFromStringId; // ebx
  unsigned __int16 *v13; // r11
  unsigned int v14; // esi
  unsigned __int16 v15; // ax
  int v16; // eax
  unsigned __int16 *v17; // rsi
  unsigned __int16 v18; // ax
  int v20; // eax
  int v21; // ecx
  const unsigned __int16 *v22; // r8
  _WORD *v23; // rax
  __int64 v24; // rdx
  unsigned int v26; // edi
  BYTE Data[8]; // [rsp+30h] [rbp-278h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-270h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-268h] BYREF
  DWORD Type; // [rsp+44h] [rbp-264h] BYREF
  int *v31; // [rsp+48h] [rbp-260h]
  WCHAR SubKey[264]; // [rsp+50h] [rbp-258h] BYREF

  v31 = a7;
  v11 = -1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MIDI2>::GetImpl'::`2'::impl)
    && CompareStringW(0x7Fu, 1u, (PCNZWCH)a1 + 80, -1, L"wdmaud2.drv", -1) == 2
    && (a4 == 2060 || a4 == 2061) )
  {
    return 0;
  }
  IdFromStringId = 0;
  if ( a4 <= 0x2015 )
  {
    if ( a4 != 8213 )
    {
      switch ( a4 )
      {
        case 0x801u:
        case 0x802u:
        case 0x803u:
        case 0x804u:
        case 0x806u:
          IdFromStringId = 8;
          goto LABEL_112;
        case 0x805u:
          lpMem = 0;
          if ( a5 || a6 )
            return 11;
          v26 = 1;
          if ( StringCbPrintfW(
                 SubKey,
                 0x20Au,
                 L"%s\\%s",
                 L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Wave Mapper",
                 (char *)a1 + 160) )
          {
            IdFromStringId = 11;
          }
          else if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, (PHKEY)&lpMem) )
          {
            Type = 0;
            cbData = 4;
            *(_DWORD *)Data = RegQueryValueExW((HKEY)lpMem, L"Mappable", 0, &Type, Data, &cbData) != 0;
            RegCloseKey((HKEY)lpMem);
            IdFromStringId = 8;
            if ( *(_DWORD *)Data )
              IdFromStringId = 0;
          }
          goto LABEL_113;
        case 0x808u:
          if ( !a5 )
            goto LABEL_111;
          *(_DWORD *)a5 = *((_DWORD *)a1 + 22);
          goto LABEL_112;
        case 0x809u:
          if ( !a5 )
            goto LABEL_111;
          *(_QWORD *)a5 = DrvGetModuleHandle(*((HDRVR *)a1 + 4));
          goto LABEL_112;
        case 0x80Au:
          if ( !(_DWORD)a6 || !a5 )
            goto LABEL_111;
          IdFromStringId = ((int)StringCchCopyW(a5, (unsigned int)(a6 - 1), (const unsigned __int16 *)a1 + 80) >> 31)
                         & 0xB;
          goto LABEL_112;
        case 0x80Cu:
          if ( !a5 )
            goto LABEL_111;
          v13 = (unsigned __int16 *)*((_QWORD *)a1 + 13);
          v14 = (unsigned int)a6 >> 1;
          if ( !v13 )
            goto LABEL_26;
          if ( *v13 == 92 && v13[1] == 92 && ((v15 = v13[2], v15 == 46) || v15 == 63) && v13[3] == 92
            || (v13 = (unsigned __int16 *)wdmPnPInterfaceFromEndpointWorker(*((const unsigned __int16 **)a1 + 13))) != 0 )
          {
            v16 = StringCchCopyW(a5, v14, v13);
            if ( v16 )
            {
              IdFromStringId = 1;
              if ( v16 == -2147024774 )
                IdFromStringId = 21;
            }
          }
          else
          {
            IdFromStringId = 7;
          }
          if ( v13 != *((unsigned __int16 **)a1 + 13) )
            HeapFree(hHeap, 0, v13);
          goto LABEL_112;
        case 0x80Du:
          if ( !a5 )
            goto LABEL_111;
          v17 = (unsigned __int16 *)*((_QWORD *)a1 + 13);
          if ( !v17 )
            goto LABEL_44;
          if ( *v17 == 92 && v17[1] == 92 && ((v18 = v17[2], v18 == 46) || v18 == 63) && v17[3] == 92
            || (v17 = (unsigned __int16 *)wdmPnPInterfaceFromEndpointWorker(*((const unsigned __int16 **)a1 + 13))) != 0 )
          {
            while ( v17[++v11] != 0 )
              ;
            v20 = ULongLongToULong(2 * v11 + 2, (unsigned int *)a5);
            v21 = 0;
            if ( v20 < 0 )
              v21 = 7;
            IdFromStringId = v21;
          }
          else
          {
            IdFromStringId = 7;
          }
          if ( v17 != *((unsigned __int16 **)a1 + 13) )
            HeapFree(hHeap, 0, v17);
          goto LABEL_112;
        case 0x80Eu:
          lpMem = 0;
          IdFromStringId = StringId_Create(a1, a3, (unsigned __int16 **)&lpMem, 0);
          if ( !IdFromStringId )
          {
            if ( (unsigned int)StringCbCopyW(a5, (unsigned int)a6, (const unsigned __int16 *)lpMem) )
              IdFromStringId = 21;
            HeapFree(hHeap, 0, lpMem);
          }
          goto LABEL_112;
        case 0x80Fu:
          if ( !a5 )
            goto LABEL_111;
          IdFromStringId = StringId_Create(a1, a3, 0, (unsigned int *)a5);
          goto LABEL_112;
        case 0x810u:
          switch ( a2 )
          {
            case 1:
              IdFromStringId = mregGetIdFromStringId(&waveoutdrvZ, a5, a6);
              break;
            case 2:
              IdFromStringId = mregGetIdFromStringId(&waveindrvZ, a5, a6);
              break;
            case 3:
              IdFromStringId = mregGetIdFromStringId(&midioutdrvZ, a5, a6);
              break;
            case 4:
              IdFromStringId = mregGetIdFromStringId(&midiindrvZ, a5, a6);
              break;
            case 8:
              IdFromStringId = mregGetIdFromStringId(&mixerdrvZ, a5, a6);
              break;
            case 10:
              IdFromStringId = mregGetIdFromStringId(&auxdrvZ, a5, a6);
              break;
            default:
              IdFromStringId = mregGetIdFromStringId(0, a5, a6);
              break;
          }
          goto LABEL_112;
        case 0x811u:
          if ( !a5 )
            goto LABEL_111;
          v22 = (const unsigned __int16 *)*((_QWORD *)a1 + 12);
          v14 = (unsigned int)a6 >> 1;
          if ( v22 )
          {
            IdFromStringId = (unsigned int)StringCchCopyW(a5, v14, v22) != 0 ? 0x15 : 0;
          }
          else
          {
LABEL_26:
            if ( v14 )
              *a5 = 0;
            else
              IdFromStringId = 21;
          }
          goto LABEL_112;
        case 0x812u:
          if ( !a5 )
            goto LABEL_111;
          if ( !*((_QWORD *)a1 + 13) )
          {
LABEL_44:
            *(_DWORD *)a5 = 2;
            goto LABEL_112;
          }
          v23 = (_WORD *)*((_QWORD *)a1 + 12);
          if ( !v23 )
            return 0;
          v24 = 0x7FFFFFFF;
          do
          {
            if ( !*v23 )
              break;
            ++v23;
            --v24;
          }
          while ( v24 );
          if ( !v24 )
            return 0;
          ULongLongToULong(2 * (0x7FFFFFFF - v24) + 2, (unsigned int *)a5);
          break;
        default:
          goto LABEL_100;
      }
      goto LABEL_112;
    }
    if ( a2 == 1 )
    {
      if ( (*((_BYTE *)a1 + 112) & 2) != 0 && a5 && a6 )
      {
        waveOutGetCurrentPreferredId(a5, a6);
LABEL_112:
        v26 = 1;
        goto LABEL_113;
      }
    }
    else if ( a2 == 2 )
    {
      if ( (*((_BYTE *)a1 + 112) & 2) != 0 && a5 && a6 )
      {
        waveInGetCurrentPreferredId(a5, a6);
        goto LABEL_112;
      }
    }
    else if ( a2 == 3 && (*((_BYTE *)a1 + 112) & 2) != 0 && a5 && a6 )
    {
      midiOutGetCurrentPreferredId(a5, a6);
      goto LABEL_112;
    }
LABEL_111:
    IdFromStringId = 11;
    goto LABEL_112;
  }
  if ( a4 == 8215 )
  {
    if ( a2 == 1 )
    {
      if ( (*((_BYTE *)a1 + 112) & 2) != 0 && a5 && a6 )
      {
        waveOutGetCurrentConsoleVoiceComId(a5, a6);
        goto LABEL_112;
      }
    }
    else if ( a2 == 2 && (*((_BYTE *)a1 + 112) & 2) != 0 && a5 && a6 )
    {
      waveInGetCurrentConsoleVoiceComId(a5, a6);
      goto LABEL_112;
    }
    goto LABEL_111;
  }
LABEL_100:
  v26 = 0;
LABEL_113:
  if ( v31 )
    *v31 = IdFromStringId;
  return v26;
}

```

## disassembly

```asm
0x180007dd0  mov     [rsp+arg_8], rbx
0x180007dd5  push    rbp
0x180007dd6  push    rsi
0x180007dd7  push    rdi
0x180007dd8  push    r12
0x180007dda  push    r13
0x180007ddc  push    r14
0x180007dde  push    r15
0x180007de0  sub     rsp, 270h
0x180007de7  mov     rax, cs:__security_cookie
0x180007dee  xor     rax, rsp
0x180007df1  mov     [rsp+2A8h+var_48], rax
0x180007df9  mov     rax, [rsp+2A8h+arg_30]
0x180007e01  mov     r13d, r9d
0x180007e04  mov     rdi, [rsp+2A8h+arg_20]
0x180007e0c  mov     r12d, r8d
0x180007e0f  mov     rsi, [rsp+2A8h+arg_28]
0x180007e17  mov     r15d, edx
0x180007e1a  mov     [rsp+2A8h+var_260], rax
0x180007e1f  mov     rbp, rcx
0x180007e22  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MIDI2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MIDI2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2> `wil::Feature<__WilFeatureTraits_Feature_MIDI2>::GetImpl(void)'::`2'::impl
0x180007e29  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MIDI2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MIDI2>::__private_IsEnabled(void)
0x180007e2e  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180007e35  test    al, al
0x180007e37  jz      short loc_180007E80
0x180007e39  lea     rax, String2; "wdmaud2.drv"
0x180007e40  mov     [rsp+2A8h+cchCount2], r14d; cchCount2
0x180007e45  lea     r8, [rbp+0A0h]; lpString1
0x180007e4c  mov     [rsp+2A8h+lpString2], rax; lpString2
0x180007e51  mov     r9d, r14d; cchCount1
0x180007e54  mov     edx, 1; dwCmpFlags
0x180007e59  mov     ecx, 7Fh; Locale
0x180007e5e  call    cs:__imp_CompareStringW
0x180007e64  cmp     eax, 2
0x180007e67  jnz     short loc_180007E80
0x180007e69  mov     eax, r13d
0x180007e6c  sub     eax, 80Ch
0x180007e71  jz      loc_1800080D7
0x180007e77  cmp     eax, 1
0x180007e7a  jz      loc_1800080D7
0x180007e80  xor     ebx, ebx
0x180007e82  cmp     r13d, 2015h
0x180007e89  ja      loc_1800083B3
0x180007e8f  jz      loc_18000832F
0x180007e95  add     r13d, 0FFFFF7FFh; switch 18 cases
0x180007e9c  cmp     r13d, 11h
0x180007ea0  ja      def_180007EB8; jumptable 0000000180007EB8 default case, cases 2055,2059
0x180007ea6  lea     rcx, __ImageBase
0x180007ead  mov     eax, ds:(jpt_180007EB8 - 180000000h)[rcx+r13*4]
0x180007eb5  add     rax, rcx
0x180007eb8  jmp     rax; switch jump
0x180007eba  test    esi, esi; jumptable 0000000180007EB8 case 2058
0x180007ebc  jz      loc_180008406
0x180007ec2  test    rdi, rdi
0x180007ec5  jz      loc_180008406
0x180007ecb  lea     r8, [rbp+0A0h]; unsigned __int16 *
0x180007ed2  mov     rcx, rdi; unsigned __int16 *
0x180007ed5  lea     edx, [rsi-1]; unsigned __int64
0x180007ed8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007edd  mov     ebx, eax
0x180007edf  sar     ebx, 1Fh
0x180007ee2  and     ebx, 0Bh
0x180007ee5  jmp     loc_18000840B
0x180007eea  mov     ebx, 8; jumptable 0000000180007EB8 cases 2049-2052,2054
0x180007eef  jmp     loc_18000840B
0x180007ef4  test    rdi, rdi; jumptable 0000000180007EB8 case 2060
0x180007ef7  jz      loc_180008406
0x180007efd  mov     r11, [rbp+68h]
0x180007f01  shr     esi, 1
0x180007f03  test    r11, r11
0x180007f06  jz      loc_180007F8F
0x180007f0c  cmp     word ptr [r11], 5Ch ; '\'
0x180007f11  jnz     short loc_180007F34
0x180007f13  cmp     word ptr [r11+2], 5Ch ; '\'
0x180007f19  jnz     short loc_180007F34
0x180007f1b  movzx   eax, word ptr [r11+4]
0x180007f20  cmp     ax, 2Eh ; '.'
0x180007f24  jz      short loc_180007F2C
0x180007f26  cmp     ax, 3Fh ; '?'
0x180007f2a  jnz     short loc_180007F34
0x180007f2c  cmp     word ptr [r11+6], 5Ch ; '\'
0x180007f32  jz      short loc_180007F4B
0x180007f34  mov     rcx, r11; unsigned __int16 *
0x180007f37  call    ?wdmPnPInterfaceFromEndpointWorker@@YAPEBGPEBG@Z; wdmPnPInterfaceFromEndpointWorker(ushort const *)
0x180007f3c  mov     r11, rax
0x180007f3f  test    rax, rax
0x180007f42  jnz     short loc_180007F4B
0x180007f44  mov     ebx, 7
0x180007f49  jmp     short loc_180007F6E
0x180007f4b  mov     edx, esi; unsigned __int64
0x180007f4d  mov     r8, r11; unsigned __int16 *
0x180007f50  mov     rcx, rdi; unsigned __int16 *
0x180007f53  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007f58  test    eax, eax
0x180007f5a  jz      short loc_180007F6E
0x180007f5c  cmp     eax, 8007007Ah
0x180007f61  mov     ebx, 1
0x180007f66  mov     ecx, 15h
0x180007f6b  cmovz   ebx, ecx
0x180007f6e  cmp     r11, [rbp+68h]
0x180007f72  jz      loc_18000840B
0x180007f78  mov     rcx, cs:hHeap; hHeap
0x180007f7f  mov     r8, r11; lpMem
0x180007f82  xor     edx, edx; dwFlags
0x180007f84  call    cs:__imp_HeapFree
0x180007f8a  jmp     loc_18000840B
0x180007f8f  cmp     esi, 1
0x180007f92  jb      short loc_180007F9E
0x180007f94  xor     eax, eax
0x180007f96  mov     [rdi], ax
0x180007f99  jmp     loc_18000840B
0x180007f9e  mov     ebx, 15h
0x180007fa3  jmp     loc_18000840B
0x180007fa8  test    rdi, rdi; jumptable 0000000180007EB8 case 2061
0x180007fab  jz      loc_180008406
0x180007fb1  mov     rsi, [rbp+68h]
0x180007fb5  test    rsi, rsi
0x180007fb8  jz      loc_18000804B
0x180007fbe  cmp     word ptr [rsi], 5Ch ; '\'
0x180007fc2  jnz     short loc_180007FE2
0x180007fc4  cmp     word ptr [rsi+2], 5Ch ; '\'
0x180007fc9  jnz     short loc_180007FE2
0x180007fcb  movzx   eax, word ptr [rsi+4]
0x180007fcf  cmp     ax, 2Eh ; '.'
0x180007fd3  jz      short loc_180007FDB
0x180007fd5  cmp     ax, 3Fh ; '?'
0x180007fd9  jnz     short loc_180007FE2
0x180007fdb  cmp     word ptr [rsi+6], 5Ch ; '\'
0x180007fe0  jz      short loc_180008000
0x180007fe2  mov     rcx, rsi; unsigned __int16 *
0x180007fe5  call    ?wdmPnPInterfaceFromEndpointWorker@@YAPEBGPEBG@Z; wdmPnPInterfaceFromEndpointWorker(ushort const *)
0x180007fea  mov     rsi, rax
0x180007fed  test    rax, rax
0x180007ff0  jnz     short loc_180008000
0x180007ff2  mov     ebx, 7
0x180007ff7  jmp     short loc_18000802A
0x180008000  cmp     [rsi+r14*2+2], bx
0x180008006  lea     r14, [r14+1]
0x18000800a  jnz     short loc_180008000
0x18000800c  lea     rcx, ds:2[r14*2]; unsigned __int64
0x180008014  mov     rdx, rdi; unsigned int *
0x180008017  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18000801c  mov     ecx, ebx
0x18000801e  test    eax, eax
0x180008020  mov     ebx, 7
0x180008025  cmovs   ecx, ebx
0x180008028  mov     ebx, ecx
0x18000802a  cmp     rsi, [rbp+68h]
0x18000802e  jz      loc_18000840B
0x180008034  mov     rcx, cs:hHeap; hHeap
0x18000803b  mov     r8, rsi; lpMem
0x18000803e  xor     edx, edx; dwFlags
0x180008040  call    cs:__imp_HeapFree
0x180008046  jmp     loc_18000840B
0x18000804b  mov     dword ptr [rdi], 2
0x180008051  jmp     loc_18000840B
0x180008056  test    rdi, rdi; jumptable 0000000180007EB8 case 2065
0x180008059  jz      loc_180008406
0x18000805f  mov     r8, [rbp+60h]; unsigned __int16 *
0x180008063  shr     esi, 1
0x180008065  test    r8, r8
0x180008068  jz      loc_180007F8F
0x18000806e  mov     edx, esi; unsigned __int64
0x180008070  mov     rcx, rdi; unsigned __int16 *
0x180008073  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008078  neg     eax
0x18000807a  sbb     ebx, ebx
0x18000807c  and     ebx, 15h
0x18000807f  jmp     loc_18000840B
0x180008084  test    rdi, rdi; jumptable 0000000180007EB8 case 2066
0x180008087  jz      loc_180008406
0x18000808d  cmp     [rbp+68h], rbx
0x180008091  jz      short loc_18000804B
0x180008093  mov     rax, [rbp+60h]
0x180008097  test    rax, rax
0x18000809a  jz      short loc_1800080D7
0x18000809c  mov     ecx, 7FFFFFFFh
0x1800080a1  mov     edx, ecx
0x1800080a3  cmp     [rax], bx
0x1800080a6  jz      short loc_1800080B2
0x1800080a8  add     rax, 2
0x1800080ac  sub     rdx, 1
0x1800080b0  jnz     short loc_1800080A3
0x1800080b2  test    rdx, rdx
0x1800080b5  jz      short loc_1800080D7
0x1800080b7  sub     rcx, rdx
0x1800080ba  xor     eax, eax
0x1800080bc  add     rcx, rcx
0x1800080bf  test    rdx, rdx
0x1800080c2  mov     rdx, rdi; unsigned int *
0x1800080c5  cmovz   rcx, rax
0x1800080c9  add     rcx, 2; unsigned __int64
0x1800080cd  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800080d2  jmp     loc_18000840B
0x1800080d7  xor     eax, eax
0x1800080d9  jmp     loc_18000841E
0x1800080de  xor     r9d, r9d; jumptable 0000000180007EB8 case 2062
0x1800080e1  mov     [rsp+2A8h+lpMem], rbx
0x1800080e6  lea     r8, [rsp+2A8h+lpMem]; unsigned __int16 **
0x1800080eb  mov     edx, r12d; unsigned int
0x1800080ee  mov     rcx, rbp; struct _MMDRV *
0x1800080f1  call    ?StringId_Create@@YAIPEAU_MMDRV@@IPEAPEAGPEAK@Z; StringId_Create(_MMDRV *,uint,ushort * *,ulong *)
0x1800080f6  mov     ebx, eax
0x1800080f8  test    eax, eax
0x1800080fa  jnz     loc_18000840B
0x180008100  mov     r8, [rsp+2A8h+lpMem]; unsigned __int16 *
0x180008105  mov     rcx, rdi; unsigned __int16 *
0x180008108  mov     edx, esi; unsigned __int64
0x18000810a  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18000810f  mov     r8, [rsp+2A8h+lpMem]; lpMem
0x180008114  test    eax, eax
0x180008116  mov     ecx, 15h
0x18000811b  cmovnz  ebx, ecx
0x18000811e  mov     rcx, cs:hHeap; hHeap
0x180008125  xor     edx, edx; dwFlags
0x180008127  call    cs:__imp_HeapFree
0x18000812d  jmp     loc_18000840B
0x180008132  test    rdi, rdi; jumptable 0000000180007EB8 case 2063
0x180008135  jz      loc_180008406
0x18000813b  mov     r9, rdi; unsigned int *
0x18000813e  xor     r8d, r8d; unsigned __int16 **
0x180008141  mov     edx, r12d; unsigned int
0x180008144  mov     rcx, rbp; struct _MMDRV *
0x180008147  call    ?StringId_Create@@YAIPEAU_MMDRV@@IPEAPEAGPEAK@Z; StringId_Create(_MMDRV *,uint,ushort * *,ulong *)
0x18000814c  mov     ebx, eax
0x18000814e  jmp     loc_18000840B
0x180008153  dec     r15d; jumptable 0000000180007EB8 case 2064
0x180008156  cmp     r15d, 9
0x18000815a  ja      def_18000816B; jumptable 000000018000816B default case, cases 5-7,9
0x180008160  mov     eax, ds:(jpt_18000816B - 180000000h)[rcx+r15*4]
0x180008168  add     rax, rcx
0x18000816b  jmp     rax; switch jump
0x18000816d  lea     rcx, waveoutdrvZ; jumptable 000000018000816B case 1
0x180008174  mov     r8, rsi
0x180008177  mov     rdx, rdi
0x18000817a  call    mregGetIdFromStringId
0x18000817f  mov     ebx, eax
0x180008181  jmp     loc_18000840B
0x180008186  lea     rcx, waveindrvZ; jumptable 000000018000816B case 2
0x18000818d  mov     r8, rsi
0x180008190  mov     rdx, rdi
0x180008193  call    mregGetIdFromStringId
0x180008198  mov     ebx, eax
0x18000819a  jmp     loc_18000840B
0x18000819f  lea     rcx, midioutdrvZ; jumptable 000000018000816B case 3
0x1800081a6  mov     r8, rsi
0x1800081a9  mov     rdx, rdi
0x1800081ac  call    mregGetIdFromStringId
0x1800081b1  mov     ebx, eax
0x1800081b3  jmp     loc_18000840B
0x1800081b8  lea     rcx, midiindrvZ; jumptable 000000018000816B case 4
0x1800081bf  mov     r8, rsi
0x1800081c2  mov     rdx, rdi
0x1800081c5  call    mregGetIdFromStringId
0x1800081ca  mov     ebx, eax
0x1800081cc  jmp     loc_18000840B
0x1800081d1  lea     rcx, auxdrvZ; jumptable 000000018000816B case 10
0x1800081d8  mov     r8, rsi
0x1800081db  mov     rdx, rdi
0x1800081de  call    mregGetIdFromStringId
0x1800081e3  mov     ebx, eax
0x1800081e5  jmp     loc_18000840B
0x1800081ea  lea     rcx, mixerdrvZ; jumptable 000000018000816B case 8
0x1800081f1  mov     r8, rsi
0x1800081f4  mov     rdx, rdi
0x1800081f7  call    mregGetIdFromStringId
0x1800081fc  mov     ebx, eax
0x1800081fe  jmp     loc_18000840B
0x180008203  xor     ecx, ecx; jumptable 000000018000816B default case, cases 5-7,9
0x180008205  mov     r8, rsi
0x180008208  mov     rdx, rdi
0x18000820b  call    mregGetIdFromStringId
0x180008210  mov     ebx, eax
0x180008212  jmp     loc_18000840B
0x180008217  mov     [rsp+2A8h+lpMem], rbx; jumptable 0000000180007EB8 case 2053
0x18000821c  test    rdi, rdi
0x18000821f  jnz     loc_1800082F8
0x180008225  test    rsi, rsi
0x180008228  jnz     loc_1800082F8
0x18000822e  lea     rax, [rbp+0A0h]
0x180008235  mov     edx, 20Ah; unsigned __int64
0x18000823a  lea     r9, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x180008241  mov     [rsp+2A8h+lpString2], rax
0x180008246  lea     r8, aSS; "%s\\%s"
0x18000824d  lea     rcx, [rsp+2A8h+SubKey]; unsigned __int16 *
0x180008252  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008257  mov     edi, 1
0x18000825c  test    eax, eax
0x18000825e  jz      short loc_18000826A
0x180008260  mov     ebx, 0Bh
0x180008265  jmp     loc_180008410
0x18000826a  lea     rax, [rsp+2A8h+lpMem]
0x18000826f  mov     r9d, edi; samDesired
0x180008272  xor     r8d, r8d; ulOptions
0x180008275  mov     [rsp+2A8h+lpString2], rax; phkResult
0x18000827a  lea     rdx, [rsp+2A8h+SubKey]; lpSubKey
0x18000827f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008286  call    cs:__imp_RegOpenKeyExW
0x18000828c  test    eax, eax
0x18000828e  jnz     loc_180008410
  ... truncated ...
```
