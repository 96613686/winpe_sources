# CSoftDist::ActSetupAdvertise(int)

- ea: `0x1800bf440`
- end: `0x1800bf7a8`
- name: `?ActSetupAdvertise@CSoftDist@@AEAAJH@Z`
- size: `872`
- prototype: `__int64 __fastcall(CSoftDist *__hidden this, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800bf7c8`

## callees

- `0x18001db50`
- `0x18002fee0`
- `0x18004d7f0`
- `0x18005789c`
- `0x18005e1c0`
- `0x18007bcc8`
- `0x1800bf440`
- `0x1800c0c44`
- `0x180128660`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800bf5ea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800bf639`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800bf684`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800bf6cf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800bf716`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800bf5ea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800bf639`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800bf684`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800bf6cf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1800bf716`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bf75d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bf75d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800bf74c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x1800bf74c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800bf572`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x1800bf572`

## string_xrefs

- `0x1800bf4e3`: `Software\Microsoft\Active Setup\Installed Components`
- `0x1800bf745`: `Precache`

## pseudocode

```c
__int64 __fastcall CSoftDist::ActSetupAdvertise(CSoftDist *this, int a2)
{
  const WCHAR *v3; // rcx
  signed int v4; // edi
  char *v5; // r14
  __int64 v6; // r15
  __int64 v7; // rax
  int v8; // edi
  char *v9; // rax
  unsigned __int64 v10; // rsi
  BOOL v11; // ebx
  int v12; // r9d
  __int64 v13; // rax
  LSTATUS v14; // esi
  const BYTE *v15; // rcx
  __int64 v16; // rax
  const BYTE *v17; // rcx
  __int64 v18; // rax
  const BYTE *v19; // rcx
  REGSAM samDesired; // [rsp+28h] [rbp-D8h]
  int lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+58h] [rbp-A8h]
  BYTE Data[16]; // [rsp+60h] [rbp-A0h] BYREF
  char v26; // [rsp+70h] [rbp-90h] BYREF

  v24 = a2;
  v3 = (const WCHAR *)*((_QWORD *)this + 2);
  hKey = 0;
  *(_QWORD *)Data = 0;
  v4 = Unicode2Ansi(v3);
  if ( v4 < 0 )
    return (unsigned int)v4;
  v5 = 0;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( *(_BYTE *)(*(_QWORD *)Data + v7) );
  v8 = v7 + 54;
  if ( (unsigned int)(v7 + 54) > 0x208 )
    v5 = (char *)operator new((unsigned int)v8);
  v9 = v5;
  if ( !v5 )
  {
    v5 = &v26;
    v8 = 520;
  }
  v10 = v8;
  v11 = v9 != 0;
  v4 = StringCchCopyA(v5, v8, "Software\\Microsoft\\Active Setup\\Installed Components");
  if ( v4 >= 0 )
  {
    v4 = StringCchCatA(v5, v10, "\\");
    if ( v4 >= 0 )
    {
      v4 = StringCchCatA(v5, v10, 0);
      if ( v4 >= 0 && !RegCreateKeyExA(HKEY_LOCAL_MACHINE, v5, 0, 0, 0, 0x2001Bu, 0, &hKey, 0) )
      {
        v12 = *((unsigned __int16 *)this + 13);
        lpSecurityAttributes = *((unsigned __int16 *)this + 14);
        samDesired = *((unsigned __int16 *)this + 15);
        *(_DWORD *)Data = 0;
        StringCchPrintfA(
          v5,
          v10,
          "%d,%d,%d,%d",
          v12,
          *((unsigned __int16 *)this + 12),
          samDesired,
          lpSecurityAttributes);
        v13 = -1;
        do
          ++v13;
        while ( v5[v13] );
        v14 = RegSetValueExA(hKey, "Version available", 0, 1u, (const BYTE *)v5, v13 + 1);
        if ( v24 || IsAbstractDifferent(hKey, *((char **)this + 9)) )
        {
          v14 = RegSetValueExA(hKey, "AdState", 0, 4u, Data, 4u);
          if ( v14 )
            goto LABEL_29;
          v15 = (const BYTE *)*((_QWORD *)this + 7);
          if ( v15 )
          {
            v16 = -1;
            do
              ++v16;
            while ( v15[v16] );
            v14 = RegSetValueExA(hKey, "Title available", 0, 1u, v15, v16 + 1);
            if ( v14 )
              goto LABEL_29;
          }
          v17 = (const BYTE *)*((_QWORD *)this + 9);
          if ( v17 )
          {
            v18 = -1;
            do
              ++v18;
            while ( v17[v18] );
            v14 = RegSetValueExA(hKey, "Abstract", 0, 1u, v17, v18 + 1);
            if ( v14 )
              goto LABEL_29;
          }
          v19 = (const BYTE *)*((_QWORD *)this + 10);
          if ( !v19 )
          {
LABEL_32:
            if ( v24 )
              RegDeleteValueA(hKey, "Precache");
            RegCloseKey(hKey);
            goto LABEL_35;
          }
          do
            ++v6;
          while ( v19[v6] );
          v14 = RegSetValueExA(hKey, "HREF available", 0, 1u, v19, v6 + 1);
        }
        if ( v14 )
        {
LABEL_29:
          if ( v14 > 0 )
            v4 = (unsigned __int16)v14 | 0x80070000;
          else
            v4 = v14;
          goto LABEL_32;
        }
        goto LABEL_32;
      }
    }
  }
LABEL_35:
  if ( v11 )
    operator delete(v5);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800bf440  push    rbp
0x1800bf442  push    rbx
0x1800bf443  push    rsi
0x1800bf444  push    rdi
0x1800bf445  push    r12
0x1800bf447  push    r13
0x1800bf449  push    r14
0x1800bf44b  push    r15
0x1800bf44d  lea     rbp, [rsp-198h]
0x1800bf455  sub     rsp, 298h
0x1800bf45c  mov     rax, cs:__security_cookie
0x1800bf463  xor     rax, rsp
0x1800bf466  mov     [rbp+1D0h+var_50], rax
0x1800bf46d  mov     [rsp+2D0h+var_278], edx
0x1800bf471  mov     r13, rcx
0x1800bf474  mov     rcx, [rcx+10h]; lpWideCharStr
0x1800bf478  lea     rdx, [rsp+2D0h+Data]
0x1800bf47d  mov     [rsp+2D0h+hKey], 0
0x1800bf486  mov     qword ptr [rsp+2D0h+Data], 0
0x1800bf48f  call    Unicode2Ansi
0x1800bf494  mov     r12, qword ptr [rsp+2D0h+Data]
0x1800bf499  mov     edi, eax
0x1800bf49b  test    eax, eax
0x1800bf49d  js      loc_1800BF775
0x1800bf4a3  xor     r14d, r14d
0x1800bf4a6  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800bf4aa  mov     rax, r15
0x1800bf4ad  inc     rax
0x1800bf4b0  cmp     [r12+rax], r14b
0x1800bf4b4  jnz     short loc_1800BF4AD
0x1800bf4b6  lea     edi, [rax+36h]
0x1800bf4b9  mov     ebx, 208h
0x1800bf4be  cmp     edi, ebx
0x1800bf4c0  jbe     short loc_1800BF4CC
0x1800bf4c2  mov     ecx, edi; Size
0x1800bf4c4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800bf4c9  mov     r14, rax
0x1800bf4cc  mov     rax, r14
0x1800bf4cf  test    r14, r14
0x1800bf4d2  jnz     short loc_1800BF4DB
0x1800bf4d4  lea     r14, [rsp+2D0h+var_260]
0x1800bf4d9  mov     edi, ebx
0x1800bf4db  xor     ebx, ebx
0x1800bf4dd  movsxd  rsi, edi
0x1800bf4e0  test    rax, rax
0x1800bf4e3  lea     r8, aSoftwareMicros_54; "Software\\Microsoft\\Active Setup\\Inst"...
0x1800bf4ea  mov     rdx, rsi; unsigned __int64
0x1800bf4ed  mov     rcx, r14; char *
0x1800bf4f0  setnz   bl
0x1800bf4f3  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800bf4f8  mov     edi, eax
0x1800bf4fa  test    eax, eax
0x1800bf4fc  js      loc_1800BF769
0x1800bf502  lea     r8, asc_18013A808; "\\"
0x1800bf509  mov     rdx, rsi; unsigned __int64
0x1800bf50c  mov     rcx, r14; char *
0x1800bf50f  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800bf514  mov     edi, eax
0x1800bf516  test    eax, eax
0x1800bf518  js      loc_1800BF769
0x1800bf51e  mov     r8, r12; char *
0x1800bf521  mov     rdx, rsi; unsigned __int64
0x1800bf524  mov     rcx, r14; char *
0x1800bf527  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800bf52c  mov     edi, eax
0x1800bf52e  test    eax, eax
0x1800bf530  js      loc_1800BF769
0x1800bf536  mov     [rsp+2D0h+lpdwDisposition], 0; lpdwDisposition
0x1800bf53f  lea     rax, [rsp+2D0h+hKey]
0x1800bf544  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800bf549  xor     r9d, r9d; lpClass
0x1800bf54c  mov     [rsp+2D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800bf555  xor     r8d, r8d; Reserved
0x1800bf558  mov     [rsp+2D0h+samDesired], 2001Bh; samDesired
0x1800bf560  mov     rdx, r14; lpSubKey
0x1800bf563  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bf56a  mov     [rsp+2D0h+dwOptions], 0; dwOptions
0x1800bf572  call    cs:__imp_RegCreateKeyExA
0x1800bf579  nop     dword ptr [rax+rax+00h]
0x1800bf57e  test    eax, eax
0x1800bf580  jnz     loc_1800BF769
0x1800bf586  movzx   ecx, word ptr [r13+1Ch]
0x1800bf58b  mov     rdx, rsi; unsigned __int64
0x1800bf58e  movzx   r8d, word ptr [r13+1Eh]
0x1800bf593  movzx   r9d, word ptr [r13+1Ah]
0x1800bf598  mov     dword ptr [rsp+2D0h+lpSecurityAttributes], ecx
0x1800bf59c  mov     rcx, r14; char *
0x1800bf59f  mov     [rsp+2D0h+samDesired], r8d
0x1800bf5a4  lea     r8, aDDDD_0; "%d,%d,%d,%d"
0x1800bf5ab  mov     dword ptr [rsp+2D0h+Data], eax
0x1800bf5af  movzx   eax, word ptr [r13+18h]
0x1800bf5b4  mov     [rsp+2D0h+dwOptions], eax
0x1800bf5b8  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800bf5bd  mov     rax, r15
0x1800bf5c0  inc     rax
0x1800bf5c3  cmp     byte ptr [r14+rax], 0
0x1800bf5c8  jnz     short loc_1800BF5C0
0x1800bf5ca  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800bf5cf  lea     rdx, aVersionAvailab; "Version available"
0x1800bf5d6  inc     eax
0x1800bf5d8  mov     r9d, 1; dwType
0x1800bf5de  mov     [rsp+2D0h+samDesired], eax; cbData
0x1800bf5e2  xor     r8d, r8d; Reserved
0x1800bf5e5  mov     qword ptr [rsp+2D0h+dwOptions], r14; lpData
0x1800bf5ea  call    cs:__imp_RegSetValueExA
0x1800bf5f1  nop     dword ptr [rax+rax+00h]
0x1800bf5f6  cmp     [rsp+2D0h+var_278], 0
0x1800bf5fb  mov     esi, eax
0x1800bf5fd  jnz     short loc_1800BF615
0x1800bf5ff  mov     rdx, [r13+48h]; char *
0x1800bf603  mov     rcx, [rsp+2D0h+hKey]; HKEY
0x1800bf608  call    ?IsAbstractDifferent@@YAHPEAUHKEY__@@PEAD@Z; IsAbstractDifferent(HKEY__ *,char *)
0x1800bf60d  test    eax, eax
0x1800bf60f  jz      loc_1800BF724
0x1800bf615  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800bf61a  lea     rax, [rsp+2D0h+Data]
0x1800bf61f  mov     r9d, 4; dwType
0x1800bf625  lea     rdx, aAdstate; "AdState"
0x1800bf62c  mov     [rsp+2D0h+samDesired], r9d; cbData
0x1800bf631  xor     r8d, r8d; Reserved
0x1800bf634  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x1800bf639  call    cs:__imp_RegSetValueExA
0x1800bf640  nop     dword ptr [rax+rax+00h]
0x1800bf645  mov     esi, eax
0x1800bf647  test    eax, eax
0x1800bf649  jnz     loc_1800BF728
0x1800bf64f  mov     rcx, [r13+38h]
0x1800bf653  test    rcx, rcx
0x1800bf656  jz      short loc_1800BF69A
0x1800bf658  mov     rax, r15
0x1800bf65b  inc     rax
0x1800bf65e  cmp     byte ptr [rcx+rax], 0
0x1800bf662  jnz     short loc_1800BF65B
0x1800bf664  inc     eax
0x1800bf666  lea     rdx, aTitleAvailable; "Title available"
0x1800bf66d  mov     [rsp+2D0h+samDesired], eax; cbData
0x1800bf671  mov     r9d, 1; dwType
0x1800bf677  mov     qword ptr [rsp+2D0h+dwOptions], rcx; lpData
0x1800bf67c  xor     r8d, r8d; Reserved
0x1800bf67f  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800bf684  call    cs:__imp_RegSetValueExA
0x1800bf68b  nop     dword ptr [rax+rax+00h]
0x1800bf690  mov     esi, eax
0x1800bf692  test    eax, eax
0x1800bf694  jnz     loc_1800BF728
0x1800bf69a  mov     rcx, [r13+48h]
0x1800bf69e  test    rcx, rcx
0x1800bf6a1  jz      short loc_1800BF6E1
0x1800bf6a3  mov     rax, r15
0x1800bf6a6  inc     rax
0x1800bf6a9  cmp     byte ptr [rcx+rax], 0
0x1800bf6ad  jnz     short loc_1800BF6A6
0x1800bf6af  inc     eax
0x1800bf6b1  lea     rdx, aAbstract_0; "Abstract"
0x1800bf6b8  mov     [rsp+2D0h+samDesired], eax; cbData
0x1800bf6bc  mov     r9d, 1; dwType
0x1800bf6c2  mov     qword ptr [rsp+2D0h+dwOptions], rcx; lpData
0x1800bf6c7  xor     r8d, r8d; Reserved
0x1800bf6ca  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800bf6cf  call    cs:__imp_RegSetValueExA
0x1800bf6d6  nop     dword ptr [rax+rax+00h]
0x1800bf6db  mov     esi, eax
0x1800bf6dd  test    eax, eax
0x1800bf6df  jnz     short loc_1800BF728
0x1800bf6e1  mov     rcx, [r13+50h]
0x1800bf6e5  test    rcx, rcx
0x1800bf6e8  jz      short loc_1800BF739
0x1800bf6ea  inc     r15
0x1800bf6ed  cmp     byte ptr [rcx+r15], 0
0x1800bf6f2  jnz     short loc_1800BF6EA
0x1800bf6f4  lea     eax, [r15+1]
0x1800bf6f8  mov     r9d, 1; dwType
0x1800bf6fe  mov     [rsp+2D0h+samDesired], eax; cbData
0x1800bf702  lea     rdx, aHrefAvailable; "HREF available"
0x1800bf709  mov     qword ptr [rsp+2D0h+dwOptions], rcx; lpData
0x1800bf70e  xor     r8d, r8d; Reserved
0x1800bf711  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800bf716  call    cs:__imp_RegSetValueExA
0x1800bf71d  nop     dword ptr [rax+rax+00h]
0x1800bf722  mov     esi, eax
0x1800bf724  test    esi, esi
0x1800bf726  jz      short loc_1800BF739
0x1800bf728  test    esi, esi
0x1800bf72a  jg      short loc_1800BF730
0x1800bf72c  mov     edi, esi
0x1800bf72e  jmp     short loc_1800BF739
0x1800bf730  movzx   edi, si
0x1800bf733  or      edi, 80070000h
0x1800bf739  cmp     [rsp+2D0h+var_278], 0
0x1800bf73e  jz      short loc_1800BF758
0x1800bf740  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800bf745  lea     rdx, aPrecache_0; "Precache"
0x1800bf74c  call    cs:__imp_RegDeleteValueA
0x1800bf753  nop     dword ptr [rax+rax+00h]
0x1800bf758  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800bf75d  call    cs:__imp_RegCloseKey
0x1800bf764  nop     dword ptr [rax+rax+00h]
0x1800bf769  test    ebx, ebx
0x1800bf76b  jz      short loc_1800BF775
0x1800bf76d  mov     rcx, r14; void *
0x1800bf770  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800bf775  test    r12, r12
0x1800bf778  jz      short loc_1800BF782
0x1800bf77a  mov     rcx, r12; void *
0x1800bf77d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800bf782  mov     eax, edi
0x1800bf784  mov     rcx, [rbp+1D0h+var_50]
0x1800bf78b  xor     rcx, rsp; StackCookie
0x1800bf78e  call    __security_check_cookie
0x1800bf793  add     rsp, 298h
0x1800bf79a  pop     r15
0x1800bf79c  pop     r14
0x1800bf79e  pop     r13
0x1800bf7a0  pop     r12
0x1800bf7a2  pop     rdi
0x1800bf7a3  pop     rsi
0x1800bf7a4  pop     rbx
0x1800bf7a5  pop     rbp
0x1800bf7a6  retn
```
