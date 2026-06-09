# ReadCipherListRegistrySetting(HKEY__ *,HKEY__ *,ushort const *)

- ea: `0x180026020`
- end: `0x180026519`
- name: `?ReadCipherListRegistrySetting@@YAXPEAUHKEY__@@0PEBG@Z`
- size: `1273`
- prototype: `void(HKEY, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x180026698`

## callees

- `0x1800061a0`
- `0x180006de0`
- `0x180007aa0`
- `0x180009770`
- `0x1800104e0`
- `0x180011fec`
- `0x180012880`
- `0x180013304`
- `0x180018150`
- `0x180022500`
- `0x180026020`
- `0x180033178`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strncat_s` at `0x1800263a8`
- `api-ms-win-crt-private-l1-1-0!_o_strncat_s` at `0x1800263cd`
- `api-ms-win-crt-private-l1-1-0!_o_strncat_s` at `0x1800263a8`
- `api-ms-win-crt-private-l1-1-0!_o_strncat_s` at `0x1800263cd`
- `api-ms-win-crt-private-l1-1-0!_o_strtok_s` at `0x18002633b`
- `api-ms-win-crt-private-l1-1-0!_o_strtok_s` at `0x180026417`
- `api-ms-win-crt-private-l1-1-0!_o_strtok_s` at `0x18002633b`
- `api-ms-win-crt-private-l1-1-0!_o_strtok_s` at `0x180026417`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002609b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026105`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002609b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180026105`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800261f3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800261f3`
- `ntdll!RtlEqualString` at `0x180026246`
- `ntdll!RtlEqualString` at `0x180026246`
- `ntdll!RtlConvertSharedToExclusive` at `0x18002647f`
- `ntdll!RtlConvertSharedToExclusive` at `0x18002647f`
- `ntdll!RtlReleaseResource` at `0x1800264f3`
- `ntdll!RtlReleaseResource` at `0x1800264f3`
- `ntdll!RtlAcquireResourceShared` at `0x180026228`
- `ntdll!RtlAcquireResourceShared` at `0x180026228`

## pseudocode

```c
void __fastcall ReadCipherListRegistrySetting(HKEY a1, HKEY a2, const unsigned __int16 *a3)
{
  HKEY v3; // rdi
  void *lpData; // rbx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  int NumberOfElementsInList; // r12d
  void *Memory; // r14
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  USHORT v12; // r15
  char *v13; // rdi
  USHORT v14; // bx
  unsigned __int16 v15; // r13
  char *v16; // rsi
  size_t v17; // r15
  unsigned __int16 v18; // si
  __int64 v19; // rbx
  struct _CIPHER_INFO near **v20; // rcx
  DWORD cbData; // [rsp+30h] [rbp-39h] BYREF
  unsigned __int16 v22; // [rsp+34h] [rbp-35h]
  DWORD Type; // [rsp+38h] [rbp-31h] BYREF
  size_t v24[2]; // [rsp+40h] [rbp-29h] BYREF
  STRING String1; // [rsp+50h] [rbp-19h] BYREF
  WINBOOL v26; // [rsp+60h] [rbp-9h] BYREF
  int v27; // [rsp+64h] [rbp-5h]
  char *Context; // [rsp+68h] [rbp-1h] BYREF
  char Delimiter[8]; // [rsp+70h] [rbp+7h] BYREF

  v3 = g_hkBase;
  strcpy(Delimiter, " ,\t\n");
  cbData = 0;
  Type = 0;
  String1 = 0;
  HIDWORD(v24[0]) = 0;
  v26 = 0;
  Context = 0;
  if ( RegQueryValueExW(g_hkBase, L"DigestEncryptionAlgorithms", 0, &Type, 0, &cbData) || Type != 1 || cbData <= 2 )
  {
    if ( a2 )
    {
      RegSetValueExW(a2, L"DigestEncryptionAlgorithms", 0, 1u, L"3des,rc4", 0x12u);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids);
    }
    goto LABEL_24;
  }
  lpData = (void *)DigestAllocateMemory(cbData);
  if ( lpData )
  {
    if ( RegQueryValueExW(v3, L"DigestEncryptionAlgorithms", 0, &Type, (LPBYTE)lpData, &cbData) )
    {
      DigestFreeMemory(lpData);
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v7 = 40;
LABEL_9:
        WPP_SF_(v6[2], v7, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids);
        return;
      }
      return;
    }
    WORD1(v24[0]) = cbData;
    v24[1] = (size_t)lpData;
    LOWORD(v24[0]) = cbData - 2;
    if ( (int)EncodeUnicodeString((unsigned __int16 *)v24, 0x6FAFu, (__int64)&String1, &v26) < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids);
      String1.Buffer = 0;
    }
    DigestFreeMemory(lpData);
LABEL_24:
    RtlAcquireResourceShared(&g_RtlResource_CipherList, 1u);
    if ( !String1.Buffer || RtlEqualString(&String1, &g_strParameter_CipherList, 1u) )
      goto LABEL_58;
    NumberOfElementsInList = (unsigned __int16)FindNumberOfElementsInList(&String1);
    Memory = (void *)DigestAllocateMemory((unsigned int)(12 * NumberOfElementsInList));
    if ( Memory )
    {
      v12 = 7 * NumberOfElementsInList;
      v27 = 7 * NumberOfElementsInList;
      v13 = (char *)DigestAllocateMemory((unsigned __int16)(7 * NumberOfElementsInList));
      if ( v13 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            46,
            &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids,
            String1.Buffer);
        v24[0] = (unsigned __int16)(7 * NumberOfElementsInList);
        memset_0(v13, 0, v24[0]);
        v14 = 0;
        v15 = 0;
        v16 = strtok_s(String1.Buffer, Delimiter, &Context);
        if ( v16 )
        {
          v17 = v24[0];
          do
          {
            if ( v15 >= (unsigned __int16)NumberOfElementsInList )
              break;
            v22 = strlencounted(v16, 6);
            v24[0] = (size_t)Memory + 12 * v15;
            if ( (int)DigestGetCipherInfo(v16) < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids, v16);
            }
            else
            {
              v18 = v22;
              strncat_s(&v13[v14], v17 - v14, (const char *)(v24[0] + 4), v22);
              v19 = (unsigned __int16)(v14 + v18);
              strncat_s(&v13[v19], v17 - v19, ",", 1u);
              v14 = v19 + 1;
              ++v15;
            }
            v16 = strtok_s(0, Delimiter, &Context);
          }
          while ( v16 );
          v12 = v27;
        }
        if ( v14 )
        {
          v12 = v14;
          v13[--v14] = 0;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids, v13);
        RtlConvertSharedToExclusive(&g_RtlResource_CipherList);
        if ( (char near **)g_strParameter_CipherList.Buffer != &g_DefaultStrCipherList )
          StringFree(&g_strParameter_CipherList);
        v20 = (struct _CIPHER_INFO near **)g_CipherInfoList;
        g_strParameter_CipherList.Buffer = v13;
        g_strParameter_CipherList.Length = v14;
        g_strParameter_CipherList.MaximumLength = v12;
        g_CipherInfoList = Memory;
        g_CipherInfoListCount = v15;
        if ( v20 && v20 != &g_DefaultCipherInfoList )
          DigestFreeMemory(v20);
        goto LABEL_58;
      }
      DigestFreeMemory(Memory);
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_58:
        StringFree(&String1);
        RtlReleaseResource(&g_RtlResource_CipherList);
        return;
      }
      v11 = 45;
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_58;
      v11 = 44;
    }
    WPP_SF_(v10[2], v11, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids);
    goto LABEL_58;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v7 = 41;
    goto LABEL_9;
  }
}

```

## disassembly

```asm
0x180026020  push    rbp
0x180026022  push    rbx
0x180026023  push    rsi
0x180026024  push    rdi
0x180026025  push    r12
0x180026027  push    r13
0x180026029  push    r14
0x18002602b  push    r15
0x18002602d  lea     rbp, [rsp-1Fh]
0x180026032  sub     rsp, 88h
0x180026039  mov     rax, cs:__security_cookie
0x180026040  xor     rax, rsp
0x180026043  mov     [rbp+57h+var_48], rax
0x180026047  mov     eax, dword ptr cs:asc_18003C2A4; " ,\t\n"
0x18002604d  lea     r9, [rbp+57h+Type]; lpType
0x180026051  mov     rdi, cs:?g_hkBase@@3PEAUHKEY__@@EA; HKEY__ * g_hkBase
0x180026058  xor     esi, esi
0x18002605a  mov     dword ptr [rbp+57h+Delimiter], eax
0x18002605d  mov     rbx, rdx
0x180026060  mov     al, byte ptr cs:asc_18003C2A4+4; ""
0x180026066  lea     rdx, ValueName; "DigestEncryptionAlgorithms"
0x18002606d  mov     [rbp+57h+var_4C], al
0x180026070  xorps   xmm0, xmm0
0x180026073  lea     rax, [rbp+57h+cbData]
0x180026077  mov     [rbp+57h+cbData], esi
0x18002607a  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18002607f  xor     r8d, r8d; lpReserved
0x180026082  mov     rcx, rdi; hKey
0x180026085  mov     [rsp+0C0h+lpData], rsi; lpData
0x18002608a  mov     [rbp+57h+Type], esi
0x18002608d  movups  xmmword ptr [rbp+57h+String1.Length], xmm0
0x180026091  mov     dword ptr [rbp+57h+var_80+4], esi
0x180026094  mov     [rbp+57h+var_60], esi
0x180026097  mov     [rbp+57h+Context], rsi
0x18002609b  call    cs:__imp_RegQueryValueExW
0x1800260a1  lea     r13, WPP_GLOBAL_Control
0x1800260a8  lea     r15, WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids
0x1800260af  lea     r12d, [rsi+1]
0x1800260b3  lea     r14d, [rsi+2]
0x1800260b7  test    eax, eax
0x1800260b9  jnz     loc_1800261CA
0x1800260bf  cmp     [rbp+57h+Type], r12d
0x1800260c3  jnz     loc_1800261CA
0x1800260c9  mov     ecx, [rbp+57h+cbData]; Size
0x1800260cc  cmp     ecx, r14d
0x1800260cf  jbe     loc_1800261CA
0x1800260d5  call    DigestAllocateMemory
0x1800260da  mov     rbx, rax
0x1800260dd  test    rax, rax
0x1800260e0  jz      loc_1800261A6
0x1800260e6  lea     rax, [rbp+57h+cbData]
0x1800260ea  xor     r8d, r8d; lpReserved
0x1800260ed  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x1800260f2  lea     r9, [rbp+57h+Type]; lpType
0x1800260f6  lea     rdx, ValueName; "DigestEncryptionAlgorithms"
0x1800260fd  mov     [rsp+0C0h+lpData], rbx; lpData
0x180026102  mov     rcx, rdi; hKey
0x180026105  call    cs:__imp_RegQueryValueExW
0x18002610b  test    eax, eax
0x18002610d  jz      short loc_180026145
0x18002610f  mov     rcx, rbx; hMem
0x180026112  call    DigestFreeMemory
0x180026117  mov     rcx, cs:WPP_GLOBAL_Control
0x18002611e  cmp     rcx, r13
0x180026121  jz      loc_1800264F9
0x180026127  test    [rcx+1Ch], r14b
0x18002612b  jz      loc_1800264F9
0x180026131  lea     edx, [rsi+28h]
0x180026134  mov     rcx, [rcx+10h]
0x180026138  mov     r8, r15
0x18002613b  call    WPP_SF_
0x180026140  jmp     loc_1800264F9
0x180026145  mov     ecx, [rbp+57h+cbData]
0x180026148  lea     r9, [rbp+57h+var_60]
0x18002614c  movzx   eax, cx
0x18002614f  mov     word ptr [rbp+57h+var_80+2], cx
0x180026153  sub     ax, r14w
0x180026157  mov     [rbp+57h+var_78], rbx
0x18002615b  lea     r8, [rbp+57h+String1]
0x18002615f  mov     word ptr [rbp+57h+var_80], ax
0x180026163  mov     edx, 6FAFh
0x180026168  lea     rcx, [rbp+57h+var_80]
0x18002616c  call    EncodeUnicodeString
0x180026171  test    eax, eax
0x180026173  jns     short loc_18002619C
0x180026175  mov     rcx, cs:WPP_GLOBAL_Control
0x18002617c  cmp     rcx, r13
0x18002617f  jz      short loc_180026198
0x180026181  test    [rcx+1Ch], r14b
0x180026185  jz      short loc_180026198
0x180026187  mov     rcx, [rcx+10h]
0x18002618b  mov     edx, 2Bh ; '+'
0x180026190  mov     r8, r15
0x180026193  call    WPP_SF_
0x180026198  mov     [rbp+57h+String1.Buffer], rsi
0x18002619c  mov     rcx, rbx; hMem
0x18002619f  call    DigestFreeMemory
0x1800261a4  jmp     short loc_18002621E
0x1800261a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800261ad  cmp     rcx, r13
0x1800261b0  jz      loc_1800264F9
0x1800261b6  test    [rcx+1Ch], r14b
0x1800261ba  jz      loc_1800264F9
0x1800261c0  mov     edx, 29h ; ')'
0x1800261c5  jmp     loc_180026134
0x1800261ca  test    rbx, rbx
0x1800261cd  jz      short loc_1800261FB
0x1800261cf  lea     rax, Data; "3des,rc4"
0x1800261d6  mov     dword ptr [rsp+0C0h+lpcbData], 12h; cbData
0x1800261de  mov     r9d, r12d; dwType
0x1800261e1  mov     [rsp+0C0h+lpData], rax; lpData
0x1800261e6  xor     r8d, r8d; Reserved
0x1800261e9  lea     rdx, ValueName; "DigestEncryptionAlgorithms"
0x1800261f0  mov     rcx, rbx; hKey
0x1800261f3  call    cs:__imp_RegSetValueExW
0x1800261f9  jmp     short loc_18002621E
0x1800261fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180026202  cmp     rcx, r13
0x180026205  jz      short loc_18002621E
0x180026207  test    byte ptr [rcx+1Ch], 4
0x18002620b  jz      short loc_18002621E
0x18002620d  mov     rcx, [rcx+10h]
0x180026211  mov     edx, 2Ah ; '*'
0x180026216  mov     r8, r15
0x180026219  call    WPP_SF_
0x18002621e  mov     dl, r12b; Wait
0x180026221  lea     rcx, g_RtlResource_CipherList; Resource
0x180026228  call    cs:__imp_RtlAcquireResourceShared
0x18002622e  cmp     [rbp+57h+String1.Buffer], rsi
0x180026232  jz      loc_1800264E3
0x180026238  mov     r8b, r12b; CaseInSensitive
0x18002623b  lea     rdx, g_strParameter_CipherList; String2
0x180026242  lea     rcx, [rbp+57h+String1]; String1
0x180026246  call    cs:__imp_RtlEqualString
0x18002624c  test    al, al
0x18002624e  jnz     loc_1800264E3
0x180026254  lea     rcx, [rbp+57h+String1]
0x180026258  call    FindNumberOfElementsInList
0x18002625d  movzx   r12d, ax
0x180026261  lea     ecx, [r12+r12*2]
0x180026265  shl     ecx, 2; Size
0x180026268  call    DigestAllocateMemory
0x18002626d  mov     r14, rax
0x180026270  test    rax, rax
0x180026273  jnz     short loc_1800262A3
0x180026275  mov     rcx, cs:WPP_GLOBAL_Control
0x18002627c  cmp     rcx, r13
0x18002627f  jz      loc_1800264E3
0x180026285  test    byte ptr [rcx+1Ch], 2
0x180026289  jz      loc_1800264E3
0x18002628f  lea     edx, [rax+2Ch]
0x180026292  mov     r8, r15
0x180026295  mov     rcx, [rcx+10h]
0x180026299  call    WPP_SF_
0x18002629e  jmp     loc_1800264E3
0x1800262a3  imul    r15d, r12d, 7
0x1800262a7  movzx   ecx, r15w; Size
0x1800262ab  mov     [rbp+57h+var_5C], r15d
0x1800262af  call    DigestAllocateMemory
0x1800262b4  mov     rdi, rax
0x1800262b7  test    rax, rax
0x1800262ba  jnz     short loc_1800262EA
0x1800262bc  mov     rcx, r14; hMem
0x1800262bf  call    DigestFreeMemory
0x1800262c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262cb  cmp     rcx, r13
0x1800262ce  jz      loc_1800264E3
0x1800262d4  test    byte ptr [rcx+1Ch], 2
0x1800262d8  jz      loc_1800264E3
0x1800262de  lea     edx, [rdi+2Dh]
0x1800262e1  lea     r8, WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids
0x1800262e8  jmp     short loc_180026295
0x1800262ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262f1  cmp     rcx, r13
0x1800262f4  jz      short loc_180026315
0x1800262f6  test    byte ptr [rcx+1Ch], 4
0x1800262fa  jz      short loc_180026315
0x1800262fc  mov     r9, [rbp+57h+String1.Buffer]
0x180026300  lea     r8, WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids
0x180026307  mov     rcx, [rcx+10h]
0x18002630b  mov     edx, 2Eh ; '.'
0x180026310  call    WPP_SF_s
0x180026315  movzx   eax, r15w
0x180026319  xor     edx, edx; Val
0x18002631b  mov     r8d, eax; Size
0x18002631e  mov     [rbp+57h+var_80], rax
0x180026322  mov     rcx, rdi; void *
0x180026325  call    memset_0
0x18002632a  mov     rcx, [rbp+57h+String1.Buffer]; String
0x18002632e  lea     r8, [rbp+57h+Context]; Context
0x180026332  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x180026336  mov     ebx, esi
0x180026338  mov     r13d, esi
0x18002633b  call    cs:__imp_strtok_s
0x180026341  xor     edx, edx
0x180026343  mov     rsi, rax
0x180026346  test    rax, rax
0x180026349  jz      loc_18002642F
0x18002634f  mov     r15, [rbp+57h+var_80]
0x180026353  cmp     r13w, r12w
0x180026357  jnb     loc_18002642B
0x18002635d  mov     edx, 6
0x180026362  mov     rcx, rsi
0x180026365  call    strlencounted
0x18002636a  movzx   ecx, r13w
0x18002636e  mov     [rbp+57h+var_8C], ax
0x180026372  lea     rdx, [rcx+rcx*2]
0x180026376  mov     rcx, rsi; String1
0x180026379  lea     rax, [r14+rdx*4]
0x18002637d  mov     rdx, rax
0x180026380  mov     [rbp+57h+var_80], rax
0x180026384  call    DigestGetCipherInfo
0x180026389  test    eax, eax
0x18002638b  js      short loc_1800263DC
0x18002638d  movzx   esi, [rbp+57h+var_8C]
0x180026391  mov     rdx, r15
0x180026394  mov     r8, [rbp+57h+var_80]
0x180026398  mov     r9d, esi; MaxCount
0x18002639b  movzx   ecx, bx
0x18002639e  add     r8, 4; Source
0x1800263a2  sub     rdx, rcx; SizeInBytes
0x1800263a5  add     rcx, rdi; Destination
0x1800263a8  call    cs:__imp_strncat_s
0x1800263ae  add     si, bx
0x1800263b1  lea     r8, asc_18003C248; ","
0x1800263b8  movzx   ebx, si
0x1800263bb  mov     rdx, r15
0x1800263be  mov     esi, 1
0x1800263c3  sub     rdx, rbx; SizeInBytes
0x1800263c6  mov     r9d, esi; MaxCount
0x1800263c9  lea     rcx, [rbx+rdi]; Destination
0x1800263cd  call    cs:__imp_strncat_s
0x1800263d3  add     bx, si
0x1800263d6  add     r13w, si
0x1800263da  jmp     short loc_18002640D
0x1800263dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800263e3  lea     rax, WPP_GLOBAL_Control
0x1800263ea  cmp     rcx, rax
0x1800263ed  jz      short loc_18002640D
0x1800263ef  test    byte ptr [rcx+1Ch], 2
0x1800263f3  jz      short loc_18002640D
0x1800263f5  mov     rcx, [rcx+10h]
0x1800263f9  lea     r8, WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids
0x180026400  mov     edx, 2Fh ; '/'
0x180026405  mov     r9, rsi
0x180026408  call    WPP_SF_s
0x18002640d  lea     r8, [rbp+57h+Context]; Context
0x180026411  xor     ecx, ecx; String
0x180026413  lea     rdx, [rbp+57h+Delimiter]; Delimiter
0x180026417  call    cs:__imp_strtok_s
0x18002641d  xor     edx, edx
0x18002641f  mov     rsi, rax
0x180026422  test    rax, rax
0x180026425  jnz     loc_180026353
0x18002642b  mov     r15d, [rbp+57h+var_5C]
0x18002642f  test    bx, bx
0x180026432  jz      short loc_180026447
0x180026434  movzx   eax, bx
0x180026437  movzx   r15d, bx
0x18002643b  mov     [rax+rdi-1], dl
0x18002643f  mov     eax, 0FFFFh
0x180026444  add     bx, ax
0x180026447  mov     rcx, cs:WPP_GLOBAL_Control
0x18002644e  lea     rax, WPP_GLOBAL_Control
0x180026455  cmp     rcx, rax
0x180026458  jz      short loc_180026478
0x18002645a  test    byte ptr [rcx+1Ch], 4
0x18002645e  jz      short loc_180026478
0x180026460  mov     rcx, [rcx+10h]
0x180026464  lea     r8, WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids
0x18002646b  mov     edx, 30h ; '0'
0x180026470  mov     r9, rdi
0x180026473  call    WPP_SF_s
0x180026478  lea     rcx, g_RtlResource_CipherList; Resource
0x18002647f  call    cs:__imp_RtlConvertSharedToExclusive
0x180026485  lea     rax, ?g_DefaultStrCipherList@@3PADA; "3des,rc4"
0x18002648c  cmp     cs:g_strParameter_CipherList.Buffer, rax
0x180026493  jz      short loc_1800264A1
0x180026495  lea     rcx, g_strParameter_CipherList
0x18002649c  call    StringFree
0x1800264a1  mov     rcx, cs:g_CipherInfoList; hMem
0x1800264a8  mov     cs:g_strParameter_CipherList.Buffer, rdi
0x1800264af  mov     cs:g_strParameter_CipherList.Length, bx
0x1800264b6  mov     cs:g_strParameter_CipherList.MaximumLength, r15w
0x1800264be  mov     cs:g_CipherInfoList, r14
0x1800264c5  mov     cs:g_CipherInfoListCount, r13w
0x1800264cd  test    rcx, rcx
0x1800264d0  jz      short loc_1800264E3
0x1800264d2  lea     rax, ?g_DefaultCipherInfoList@@3PAU_CIPHER_INFO@@A; _CIPHER_INFO near * g_DefaultCipherInfoList
0x1800264d9  cmp     rcx, rax
0x1800264dc  jz      short loc_1800264E3
0x1800264de  call    DigestFreeMemory
0x1800264e3  lea     rcx, [rbp+57h+String1]
0x1800264e7  call    StringFree
0x1800264ec  lea     rcx, g_RtlResource_CipherList; Resource
0x1800264f3  call    cs:__imp_RtlReleaseResource
0x1800264f9  mov     rcx, [rbp+57h+var_48]
0x1800264fd  xor     rcx, rsp; StackCookie
0x180026500  call    __security_check_cookie
0x180026505  add     rsp, 88h
  ... truncated ...
```
