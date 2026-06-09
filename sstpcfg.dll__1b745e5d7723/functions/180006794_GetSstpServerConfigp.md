# GetSstpServerConfigp

- ea: `0x180006794`
- end: `0x180006a15`
- name: `GetSstpServerConfigp`
- size: `641`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180006590`
- `0x180009720`

## callees

- `0x180006794`
- `0x18000a014`
- `0x18000a044`
- `0x18000acbc`
- `0x18000ae4e`
- `0x18000ae80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000681e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000691e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000681e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000691e`

## pseudocode

```c
__int64 __fastcall GetSstpServerConfigp(HKEY hKey, __int64 a2)
{
  unsigned int v4; // eax
  __int64 v5; // r8
  unsigned int v6; // edi
  __int64 v7; // rdx
  const wchar_t *v8; // r8
  bool v9; // al
  unsigned int v10; // eax
  __int64 v11; // r8
  unsigned int v12; // edi
  __int64 result; // rax
  __int64 v14; // rdx
  const wchar_t *v15; // r8
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[2044]; // [rsp+44h] [rbp-BCh] BYREF

  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  v4 = RegQueryValueExW(hKey, L"UseHttps", 0, &Type, Data, &cbData);
  v6 = v4;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v5, v4);
    }
    if ( !(_QWORD)xmmword_1800146E0 )
      goto LABEL_17;
    LOWORD(v19) = 0;
    FormatRRASErrorString(&v19, L"UseHttps lookup fails with error %d. Using default", v6);
    v7 = xmmword_1800146E0;
    v8 = (const wchar_t *)&v19;
    goto LABEL_16;
  }
  if ( Type == 4 )
  {
    v9 = *(_DWORD *)Data != 0;
    goto LABEL_18;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25);
  }
  v7 = xmmword_1800146E0;
  if ( (_QWORD)xmmword_1800146E0 )
  {
    v8 = L"UseHttps: Type is invalid. Using default value";
LABEL_16:
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, v7, v8);
  }
LABEL_17:
  v9 = 1;
LABEL_18:
  *(_BYTE *)a2 = v9;
  cbData = 4;
  v10 = RegQueryValueExW(hKey, L"ListenerPort", 0, &Type, Data, &cbData);
  v12 = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v11, v10);
    }
    if ( !(_QWORD)xmmword_1800146E0 )
      goto LABEL_34;
    LOWORD(v19) = 0;
    FormatRRASErrorString(&v19, L"ListenerPort couldn't be queried. %d", v12);
    v14 = xmmword_1800146E0;
    v15 = (const wchar_t *)&v19;
    goto LABEL_33;
  }
  if ( Type != 4 || (result = *(unsigned int *)Data, *(_DWORD *)Data > 0xFFFFu) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27);
    }
    v14 = xmmword_1800146E0;
    if ( !(_QWORD)xmmword_1800146E0 )
      goto LABEL_34;
    v15 = L"ListenerPort value is out of range or invalid. Reverting to default";
LABEL_33:
    ((void (__fastcall *)(__int64, __int64, const wchar_t *))gSstpCfgTemplateFunc)(gSstpCfgEtwContext, v14, v15);
LABEL_34:
    result = 0;
  }
  *(_WORD *)(a2 + 2) = result;
  return result;
}

```

## disassembly

```asm
0x180006794  mov     [rsp-8+arg_10], rbx
0x180006799  mov     [rsp-8+arg_18], rsi
0x18000679e  push    rbp
0x18000679f  push    rdi
0x1800067a0  push    r14
0x1800067a2  lea     rbp, [rsp-750h]
0x1800067aa  sub     rsp, 850h
0x1800067b1  mov     rax, cs:__security_cookie
0x1800067b8  xor     rax, rsp
0x1800067bb  mov     [rbp+760h+var_20], rax
0x1800067c2  mov     rsi, rdx
0x1800067c5  mov     [rsp+860h+Type], 0
0x1800067cd  mov     r14, rcx
0x1800067d0  mov     dword ptr [rsp+860h+Data], 0
0x1800067d8  xor     eax, eax
0x1800067da  mov     [rsp+860h+cbData], 4
0x1800067e2  xor     edx, edx; Val
0x1800067e4  mov     [rsp+860h+var_820], eax
0x1800067e8  lea     rcx, [rsp+860h+var_81C]; void *
0x1800067ed  mov     r8d, 7FCh; Size
0x1800067f3  call    memset_0
0x1800067f8  lea     rax, [rsp+860h+cbData]
0x1800067fd  xor     r8d, r8d; lpReserved
0x180006800  mov     [rsp+860h+lpcbData], rax; lpcbData
0x180006805  lea     r9, [rsp+860h+Type]; lpType
0x18000680a  lea     rax, [rsp+860h+Data]
0x18000680f  mov     rcx, r14; hKey
0x180006812  lea     rdx, aUsehttps; "UseHttps"
0x180006819  mov     [rsp+860h+lpData], rax; lpData
0x18000681e  call    cs:__imp_RegQueryValueExW
0x180006824  lea     rbx, WPP_GLOBAL_Control
0x18000682b  mov     edi, eax
0x18000682d  test    eax, eax
0x18000682f  jnz     short loc_18000687F
0x180006831  cmp     [rsp+860h+Type], 4
0x180006836  jz      short loc_180006875
0x180006838  mov     rcx, cs:WPP_GLOBAL_Control
0x18000683f  cmp     rcx, rbx
0x180006842  jz      short loc_18000685C
0x180006844  test    byte ptr [rcx+1Ch], 40h
0x180006848  jz      short loc_18000685C
0x18000684a  cmp     byte ptr [rcx+19h], 2
0x18000684e  jb      short loc_18000685C
0x180006850  mov     rcx, [rcx+10h]
0x180006854  lea     edx, [rax+19h]
0x180006857  call    WPP_SF_
0x18000685c  mov     rdx, qword ptr cs:xmmword_1800146E0
0x180006863  test    rdx, rdx
0x180006866  jz      loc_1800068EC
0x18000686c  lea     r8, aUsehttpsTypeIs; "UseHttps: Type is invalid. Using defaul"...
0x180006873  jmp     short loc_1800068D9
0x180006875  cmp     dword ptr [rsp+860h+Data], 0
0x18000687a  setnz   al
0x18000687d  jmp     short loc_1800068EE
0x18000687f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006886  cmp     rcx, rbx
0x180006889  jz      short loc_1800068A8
0x18000688b  test    byte ptr [rcx+1Ch], 40h
0x18000688f  jz      short loc_1800068A8
0x180006891  cmp     byte ptr [rcx+19h], 2
0x180006895  jb      short loc_1800068A8
0x180006897  mov     rcx, [rcx+10h]
0x18000689b  mov     edx, 1Ah
0x1800068a0  mov     r9d, edi
0x1800068a3  call    WPP_SF_d
0x1800068a8  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800068b0  jz      short loc_1800068EC
0x1800068b2  xor     eax, eax
0x1800068b4  lea     rdx, aUsehttpsLookup; "UseHttps lookup fails with error %d. Us"...
0x1800068bb  mov     r8d, edi
0x1800068be  mov     word ptr [rsp+860h+var_820], ax
0x1800068c3  lea     rcx, [rsp+860h+var_820]
0x1800068c8  call    FormatRRASErrorString
0x1800068cd  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800068d4  lea     r8, [rsp+860h+var_820]
0x1800068d9  mov     rcx, cs:gSstpCfgEtwContext
0x1800068e0  mov     rax, cs:gSstpCfgTemplateFunc
0x1800068e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068ec  mov     al, 1
0x1800068ee  mov     [rsi], al
0x1800068f0  lea     r9, [rsp+860h+Type]; lpType
0x1800068f5  lea     rax, [rsp+860h+cbData]
0x1800068fa  mov     [rsp+860h+cbData], 4
0x180006902  mov     [rsp+860h+lpcbData], rax; lpcbData
0x180006907  lea     rdx, ValueName; "ListenerPort"
0x18000690e  lea     rax, [rsp+860h+Data]
0x180006913  xor     r8d, r8d; lpReserved
0x180006916  mov     rcx, r14; hKey
0x180006919  mov     [rsp+860h+lpData], rax; lpData
0x18000691e  call    cs:__imp_RegQueryValueExW
0x180006924  mov     edi, eax
0x180006926  test    eax, eax
0x180006928  jnz     short loc_18000697B
0x18000692a  cmp     [rsp+860h+Type], 4
0x18000692f  jnz     short loc_180006940
0x180006931  mov     eax, dword ptr [rsp+860h+Data]
0x180006935  cmp     eax, 0FFFFh
0x18000693a  jbe     loc_1800069EA
0x180006940  mov     rcx, cs:WPP_GLOBAL_Control
0x180006947  cmp     rcx, rbx
0x18000694a  jz      short loc_180006966
0x18000694c  test    byte ptr [rcx+1Ch], 40h
0x180006950  jz      short loc_180006966
0x180006952  cmp     byte ptr [rcx+19h], 2
0x180006956  jb      short loc_180006966
0x180006958  mov     rcx, [rcx+10h]
0x18000695c  mov     edx, 1Bh
0x180006961  call    WPP_SF_
0x180006966  mov     rdx, qword ptr cs:xmmword_1800146E0
0x18000696d  test    rdx, rdx
0x180006970  jz      short loc_1800069E8
0x180006972  lea     r8, aListenerportVa; "ListenerPort value is out of range or i"...
0x180006979  jmp     short loc_1800069D5
0x18000697b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006982  cmp     rcx, rbx
0x180006985  jz      short loc_1800069A4
0x180006987  test    byte ptr [rcx+1Ch], 40h
0x18000698b  jz      short loc_1800069A4
0x18000698d  cmp     byte ptr [rcx+19h], 2
0x180006991  jb      short loc_1800069A4
0x180006993  mov     rcx, [rcx+10h]
0x180006997  mov     edx, 1Ch
0x18000699c  mov     r9d, edi
0x18000699f  call    WPP_SF_d
0x1800069a4  cmp     qword ptr cs:xmmword_1800146E0, 0
0x1800069ac  jz      short loc_1800069E8
0x1800069ae  xor     eax, eax
0x1800069b0  lea     rdx, aListenerportCo; "ListenerPort couldn't be queried. %d"
0x1800069b7  mov     r8d, edi
0x1800069ba  mov     word ptr [rsp+860h+var_820], ax
0x1800069bf  lea     rcx, [rsp+860h+var_820]
0x1800069c4  call    FormatRRASErrorString
0x1800069c9  mov     rdx, qword ptr cs:xmmword_1800146E0
0x1800069d0  lea     r8, [rsp+860h+var_820]
0x1800069d5  mov     rcx, cs:gSstpCfgEtwContext
0x1800069dc  mov     rax, cs:gSstpCfgTemplateFunc
0x1800069e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069e8  xor     eax, eax
0x1800069ea  mov     [rsi+2], ax
0x1800069ee  mov     rcx, [rbp+760h+var_20]
0x1800069f5  xor     rcx, rsp; StackCookie
0x1800069f8  call    __security_check_cookie
0x1800069fd  lea     r11, [rsp+860h+var_10]
0x180006a05  mov     rbx, [r11+30h]
0x180006a09  mov     rsi, [r11+38h]
0x180006a0d  mov     rsp, r11
0x180006a10  pop     r14
0x180006a12  pop     rdi
0x180006a13  pop     rbp
0x180006a14  retn
```
