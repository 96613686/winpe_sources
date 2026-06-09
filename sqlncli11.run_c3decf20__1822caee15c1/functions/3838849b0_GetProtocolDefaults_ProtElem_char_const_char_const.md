# GetProtocolDefaults(ProtElem *,char const *,char const *)

- ea: `0x3838849b0`
- end: `0x383884ba4`
- name: `?GetProtocolDefaults@@YAKPEAVProtElem@@PEBD1@Z`
- size: `500`
- prototype: `unsigned int(struct ProtElem *, const char *, const char *)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x383883940`
- `0x38388f8a0`

## callees

- `0x3838434c0`
- `0x3838435e0`
- `0x38387d300`
- `0x38387dae0`
- `0x3838849b0`
- `0x383884bb0`
- `0x383884c30`
- `0x383884e30`
- `0x38388f760`
- `0x38391ac00`
- `0x38391ac40`
- `0x38391ae80`
- `0x38391af20`

## import_xrefs

- `MSVCR100!free` at `0x3839020e1`
- `MSVCR100!free` at `0x38390215c`
- `MSVCR100!free` at `0x3839020e1`
- `MSVCR100!free` at `0x38390215c`
- `MSVCR100!_dupenv_s` at `0x38388fc0c`
- `MSVCR100!_dupenv_s` at `0x38388fc0c`
- `MSVCR100!_stricmp` at `0x383902090`
- `MSVCR100!_stricmp` at `0x383902090`
- `KERNEL32!CompareStringA` at `0x38388fc95`
- `KERNEL32!CompareStringA` at `0x38388fc95`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetProtocolDefaults(struct ProtElem *a1, const char *a2, const char *a3)
{
  int v6; // esi
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  __int64 v10; // rbx
  int v11; // edi
  __int64 v13; // rdx
  _BYTE *v14; // rcx
  __int64 v15; // rbx
  char v16; // al
  bool v17; // sf
  __int64 v18; // rdx
  char *v19; // r14
  char *v20; // rcx
  CHAR v21; // al
  int v22; // ebx
  __int64 v23; // rcx
  char *v24; // rax
  __int64 v25; // rdi
  char *v26; // rax
  __int64 v27; // rcx
  char *v28; // r8
  char v29; // dl
  _BYTE *v30; // rcx
  char v31; // al
  PCNZCH lpString2; // [rsp+20h] [rbp-E0h]
  __int16 v33[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v34; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  char *Buffer; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-A8h] BYREF
  int v38; // [rsp+60h] [rbp-A0h]
  HKEY v39; // [rsp+68h] [rbp-98h] BYREF
  int v40; // [rsp+70h] [rbp-90h]
  int v41; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v42; // [rsp+78h] [rbp-88h]
  _DWORD v43[132]; // [rsp+80h] [rbp-80h] BYREF

  v42 = -2;
  v35 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B48A88[0] )
  {
    LODWORD(lpString2) = (_DWORD)a3;
    bidScopeEnterA(&v35, off_383B48A88[0], a1);
  }
  v6 = 0;
  Buffer = 0;
  if ( GetProtocolEnum(a2, (enum ProviderNum *)&v41) )
    goto LABEL_81;
  v7 = v41;
  *(_DWORD *)a1 = v41;
  if ( v7 == 7 )
    *((_BYTE *)a1 + 776) = 0;
  v8 = v7 - 1;
  if ( v8 )
  {
    v9 = v8 - 3;
    if ( v9 )
    {
      if ( v9 == 3 )
      {
        v10 = 256;
        if ( g_fSandbox )
          goto LABEL_66;
        v33[0] = 11;
        lpMem = 0;
        v40 = 256;
        if ( !a2 || !v43 )
          goto LABEL_66;
        v11 = NLregC::CSgetSNISubRegKey((NLregC *)v33, a2, (HKEY *)&lpMem, 1u, 0);
        if ( !v11 )
        {
          memset(v43, 0, 0x204u);
          v43[64] = 0;
          lpString2 = (PCNZCH)&v43[64];
          v11 = NLregC::CSgetFlagOrProperty(lpMem, 1, 1, v43);
        }
        if ( lpMem )
          IniRegCloseKey(lpMem);
        if ( !v11 && v43[64] == 4 )
        {
          StringCchPrintfA((char *)a1 + 520, 0x100u, "%d", v43[65]);
        }
        else
        {
LABEL_66:
          v30 = (char *)a1 + 520;
          while ( v10 != -2147483390 )
          {
            v31 = v30["1433" - ((char *)a1 + 520)];
            if ( !v31 )
              break;
            *v30++ = v31;
            if ( !--v10 )
            {
              --v30;
              break;
            }
          }
          *v30 = 0;
        }
        goto LABEL_18;
      }
      if ( (bidGblFlags & 2) != 0 && off_383B477D8[0] && bidID != -1 )
      {
        LODWORD(lpString2) = 0;
        off_383B15038();
      }
      goto LABEL_81;
    }
    v13 = 512;
    v14 = (char *)a1 + 520;
    v15 = a3 - ((const char *)a1 + 520);
    while ( v13 != -2147483134 )
    {
      v16 = v14[v15];
      if ( !v16 )
        break;
      *v14++ = v16;
      if ( !--v13 )
      {
        --v14;
        v6 = -2147024774;
        break;
      }
    }
    *v14 = 0;
    v17 = v6 < 0;
    goto LABEL_29;
  }
  if ( !_dupenv_s(&Buffer, 0, "_CLUSTER_NETWORK_NAME_") )
  {
    v18 = 261;
    v19 = (char *)a1 + 520;
    v20 = v19;
    while ( v18 != -2147483385 )
    {
      v21 = v20["\\\\" - v19];
      if ( !v21 )
        break;
      *v20++ = v21;
      if ( !--v18 )
      {
        --v20;
        break;
      }
    }
    *v20 = 0;
    if ( CompareStringA(0x800u, 0x20001u, a3, -1, gszComputerName, -1) == 2
      && (!Buffer || !_stricmp(Buffer, &byte_38387C772)) )
    {
      StringCchCatA(v19, 0x105u, ".");
    }
    else if ( (int)StringCchCatA(v19, 0x105u, a3) < 0 )
    {
      goto LABEL_81;
    }
    if ( (int)StringCchCatA(v19, 0x105u, "\\PIPE\\") >= 0 )
    {
      if ( g_fSandbox )
        goto LABEL_75;
      v34 = 11;
      v39 = 0;
      v38 = 256;
      if ( !a2 || !v43 )
        goto LABEL_75;
      v22 = NLregC::CSgetSNISubRegKey((NLregC *)&v34, a2, &v39, 1u, 0);
      if ( !v22 )
      {
        memset(v43, 0, 0x204u);
        v43[64] = 0;
        lpString2 = (PCNZCH)&v43[64];
        v22 = NLregC::CSgetFlagOrProperty(v39, 1, 1, v43);
      }
      if ( v39 )
        IniRegCloseKey(v39);
      if ( !v22 && v43[64] == 1 )
      {
        v23 = 261;
        v24 = v19;
        while ( *v24 )
        {
          ++v24;
          if ( !--v23 )
            goto LABEL_81;
        }
        v25 = v23;
        v26 = &v19[261 - v23];
        v27 = 0x7FFFFFFF;
        v28 = (char *)((char *)&v43[65] - v26);
        while ( v27 )
        {
          v29 = v28[(_QWORD)v26];
          if ( !v29 )
            break;
          *v26++ = v29;
          --v27;
          if ( !--v25 )
          {
            --v26;
            v6 = -2147024774;
            break;
          }
        }
        *v26 = 0;
        v17 = v6 < 0;
      }
      else
      {
LABEL_75:
        v17 = (int)StringCchCatA(v19, 0x105u, "sql\\query") < 0;
      }
LABEL_29:
      if ( !v17 )
      {
LABEL_18:
        if ( Buffer )
          free(Buffer);
        if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B477D0[0] )
          bidTraceA(off_383B45150[0], 985088, off_383B477D0[0], 0, (_DWORD)lpString2);
        if ( v35 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
          off_383B15058();
        return 0;
      }
    }
  }
LABEL_81:
  if ( Buffer )
    free(Buffer);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B477C8[0] )
    bidTraceA(off_383B45148[0], 996352, off_383B477C8[0], 0xFFFFFFFFLL, (_DWORD)lpString2);
  if ( v35 != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x3838849b0  push    rbp
0x3838849b2  push    rsi
0x3838849b3  push    rdi
0x3838849b4  push    r14
0x3838849b6  push    r15
0x3838849b8  lea     rbp, [rsp-1A0h]
0x3838849c0  sub     rsp, 2A0h
0x3838849c7  mov     [rsp+2C0h+var_248], 0FFFFFFFFFFFFFFFEh
0x3838849d0  mov     [rsp+2C0h+arg_18], rbx
0x3838849d8  mov     rax, cs:__security_cookie
0x3838849df  xor     rax, rsp
0x3838849e2  mov     [rbp+1C0h+var_30], rax
0x3838849e9  mov     rbx, r8
0x3838849ec  mov     r15, rdx
0x3838849ef  mov     r14, rcx
0x3838849f2  mov     [rsp+2C0h+var_278], 0FFFFFFFFFFFFFFFFh
0x3838849fb  mov     eax, cs:_bidGblFlags
0x383884a01  and     eax, 20004h
0x383884a06  cmp     eax, 20004h
0x383884a0b  jz      loc_383901F99
0x383884a11  xor     esi, esi
0x383884a13  mov     [rsp+2C0h+Buffer], rsi
0x383884a18  lea     rdx, [rsp+2C0h+var_24C]; enum ProviderNum *
0x383884a1d  mov     rcx, r15; String2
0x383884a20  call    ?GetProtocolEnum@@YAKPEBDPEAW4ProviderNum@@@Z; GetProtocolEnum(char const *,ProviderNum *)
0x383884a25  test    eax, eax
0x383884a27  jnz     loc_383902152
0x383884a2d  mov     ecx, [rsp+2C0h+var_24C]
0x383884a31  mov     [r14], ecx
0x383884a34  cmp     ecx, 7
0x383884a37  jnz     short loc_383884A40
0x383884a39  mov     [r14+308h], sil
0x383884a40  dec     ecx
0x383884a42  jz      loc_38388FBFE
0x383884a48  sub     ecx, 3
0x383884a4b  jz      loc_38388FBA6
0x383884a51  cmp     ecx, 3
0x383884a54  jnz     loc_383901FCB
0x383884a5a  mov     ebx, 100h
0x383884a5f  cmp     cs:?g_fSandbox@@3HA, esi; int g_fSandbox
0x383884a65  jnz     loc_383902021
0x383884a6b  mov     eax, 0Bh
0x383884a70  mov     [rsp+2C0h+var_280], ax
0x383884a75  mov     [rsp+2C0h+lpMem], rsi
0x383884a7a  mov     [rsp+2C0h+var_250], ebx
0x383884a7e  test    r15, r15
0x383884a81  jz      loc_383902021
0x383884a87  lea     rax, [rbp+1C0h+var_240]
0x383884a8b  test    rax, rax
0x383884a8e  jz      loc_383902021
0x383884a94  mov     dword ptr [rsp+2C0h+lpString2], esi; int
0x383884a98  mov     r9d, 1; unsigned int
0x383884a9e  lea     r8, [rsp+2C0h+lpMem]; HKEY *
0x383884aa3  mov     rdx, r15; char *
0x383884aa6  lea     rcx, [rsp+2C0h+var_280]; this
0x383884aab  call    ?CSgetSNISubRegKey@NLregC@@AEAAJPEBDPEAPEAUHKEY__@@KH@Z; NLregC::CSgetSNISubRegKey(char const *,HKEY__ * *,ulong,int)
0x383884ab0  mov     edi, eax
0x383884ab2  test    eax, eax
0x383884ab4  jnz     short loc_383884B07
0x383884ab6  xor     edx, edx; Val
0x383884ab8  mov     r8d, 204h; Size
0x383884abe  lea     rcx, [rbp+1C0h+var_240]; void *
0x383884ac2  call    memset
0x383884ac7  mov     [rbp+1C0h+var_140], esi
0x383884acd  lea     rax, [rsp+2C0h+var_250]
0x383884ad2  mov     [rsp+2C0h+var_290], rax
0x383884ad7  lea     rax, [rbp+1C0h+var_13C]
0x383884ade  mov     qword ptr [rsp+2C0h+cchCount2], rax
0x383884ae3  lea     rax, [rbp+1C0h+var_140]
0x383884aea  mov     [rsp+2C0h+lpString2], rax
0x383884aef  lea     r9, [rbp+1C0h+var_240]
0x383884af3  mov     edx, 1
0x383884af8  mov     r8d, edx
0x383884afb  mov     rcx, [rsp+2C0h+lpMem]
0x383884b00  call    ?CSgetFlagOrProperty@NLregC@@AEAAJPEAUHKEY__@@W4CSFPVTYPE@@KPEADKPEAKPEAE3@Z; NLregC::CSgetFlagOrProperty(HKEY__ *,CSFPVTYPE,ulong,char *,ulong,ulong *,uchar *,ulong *)
0x383884b05  mov     edi, eax
0x383884b07  mov     rcx, [rsp+2C0h+lpMem]; lpMem
0x383884b0c  test    rcx, rcx
0x383884b0f  jz      short loc_383884B16
0x383884b11  call    IniRegCloseKey
0x383884b16  test    edi, edi
0x383884b18  jnz     loc_383902021
0x383884b1e  cmp     [rbp+1C0h+var_140], 4
0x383884b25  jnz     loc_383902021
0x383884b2b  lea     rcx, [r14+208h]; char *
0x383884b32  mov     r9d, [rbp+1C0h+var_13C]
0x383884b39  lea     r8, aD_0; "%d"
0x383884b40  mov     rdx, rbx; unsigned __int64
0x383884b43  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x383884b48  jmp     short $+2
0x383884b4a  mov     rcx, [rsp+2C0h+Buffer]; Block
0x383884b4f  test    rcx, rcx
0x383884b52  jnz     loc_3839020E1
0x383884b58  mov     eax, cs:_bidGblFlags
0x383884b5e  and     eax, 20002h
0x383884b63  cmp     eax, 20002h
0x383884b68  jz      loc_3839020ED
0x383884b6e  cmp     [rsp+2C0h+var_278], 0FFFFFFFFFFFFFFFFh
0x383884b74  jnz     loc_38390211E
0x383884b7a  xor     eax, eax
0x383884b7c  jmp     short $+2
0x383884b7e  mov     rcx, [rbp+1C0h+var_30]
0x383884b85  xor     rcx, rsp; StackCookie
0x383884b88  call    __security_check_cookie
0x383884b8d  mov     rbx, [rsp+2C0h+arg_18]
0x383884b95  add     rsp, 2A0h
0x383884b9c  pop     r15
0x383884b9e  pop     r14
0x383884ba0  pop     rdi
0x383884ba1  pop     rsi
0x383884ba2  pop     rbp
0x383884ba3  retn
0x38388fba6  mov     edx, 200h
0x38388fbab  lea     rcx, [r14+208h]
0x38388fbb2  sub     rbx, rcx
0x38388fbb5  nop     word ptr [rax+rax+00000000h]
0x38388fbc0  lea     rax, [rdx+7FFFFDFEh]
0x38388fbc7  test    rax, rax
0x38388fbca  jz      short loc_38388FBE3
0x38388fbcc  movzx   eax, byte ptr [rbx+rcx]
0x38388fbd0  test    al, al
0x38388fbd2  jz      short loc_38388FBE3
0x38388fbd4  mov     [rcx], al
0x38388fbd6  inc     rcx
0x38388fbd9  dec     rdx
0x38388fbdc  jnz     short loc_38388FBC0
0x38388fbde  jmp     loc_383902070
0x38388fbe3  test    rdx, rdx
0x38388fbe6  jz      loc_383902072
0x38388fbec  mov     byte ptr [rcx], 0
0x38388fbef  test    esi, esi
0x38388fbf1  jmp     short $+2
0x38388fbf3  jns     loc_383884B4A
0x38388fbf9  jmp     loc_383902152
0x38388fbfe  lea     r8, VarName; "_CLUSTER_NETWORK_NAME_"
0x38388fc05  xor     edx, edx; BufferCount
0x38388fc07  lea     rcx, [rsp+2C0h+Buffer]; Buffer
0x38388fc0c  call    cs:__imp__dupenv_s
0x38388fc12  test    eax, eax
0x38388fc14  jnz     loc_383902152
0x38388fc1a  mov     edi, 105h
0x38388fc1f  mov     edx, edi
0x38388fc21  add     r14, 208h
0x38388fc28  mov     rcx, r14
0x38388fc2b  lea     r8, Str2; "\\\\"
0x38388fc32  sub     r8, r14
0x38388fc35  nop     word ptr [rax+rax+00000000h]
0x38388fc40  lea     rax, [rdx+7FFFFEF9h]
0x38388fc47  test    rax, rax
0x38388fc4a  jz      short loc_38388FC64
0x38388fc4c  movzx   eax, byte ptr [r8+rcx]
0x38388fc51  test    al, al
0x38388fc53  jz      short loc_38388FC64
0x38388fc55  mov     [rcx], al
0x38388fc57  inc     rcx
0x38388fc5a  dec     rdx
0x38388fc5d  jnz     short loc_38388FC40
0x38388fc5f  jmp     loc_38390207F
0x38388fc64  test    rdx, rdx
0x38388fc67  jz      loc_383902081
0x38388fc6d  mov     [rcx], sil
0x38388fc70  mov     [rsp+2C0h+cchCount2], 0FFFFFFFFh; cchCount2
0x38388fc78  lea     rax, ?gszComputerName@@3PADA; char near * gszComputerName
0x38388fc7f  mov     [rsp+2C0h+lpString2], rax; lpString2
0x38388fc84  or      r9d, 0FFFFFFFFh; cchCount1
0x38388fc88  mov     r8, rbx; lpString1
0x38388fc8b  mov     edx, 20001h; dwCmpFlags
0x38388fc90  mov     ecx, 800h; Locale
0x38388fc95  call    cs:__imp_CompareStringA
0x38388fc9b  cmp     eax, 2
0x38388fc9e  jnz     loc_38390209E
0x38388fca4  mov     rcx, [rsp+2C0h+Buffer]; String1
0x38388fca9  test    rcx, rcx
0x38388fcac  jnz     loc_383902089
0x38388fcb2  lea     r8, asc_38387C770; "."
0x38388fcb9  mov     rdx, rdi; unsigned __int64
0x38388fcbc  mov     rcx, r14; char *
0x38388fcbf  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x38388fcc4  jmp     short $+2
0x38388fcc6  lea     r8, aPipe; "\\PIPE\\"
0x38388fccd  mov     rdx, rdi; unsigned __int64
0x38388fcd0  mov     rcx, r14; char *
0x38388fcd3  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x38388fcd8  test    eax, eax
0x38388fcda  js      loc_383902152
0x38388fce0  cmp     cs:?g_fSandbox@@3HA, esi; int g_fSandbox
0x38388fce6  jnz     loc_3839020C8
0x38388fcec  mov     eax, 0Bh
0x38388fcf1  mov     [rsp+2C0h+var_27C], ax
0x38388fcf6  mov     [rsp+2C0h+var_258], rsi
0x38388fcfb  mov     ebx, 100h
0x38388fd00  mov     [rsp+2C0h+var_260], ebx
0x38388fd04  test    r15, r15
0x38388fd07  jz      loc_3839020C8
0x38388fd0d  lea     rax, [rbp+1C0h+var_240]
0x38388fd11  test    rax, rax
0x38388fd14  jz      loc_3839020C8
0x38388fd1a  mov     dword ptr [rsp+2C0h+lpString2], esi; int
0x38388fd1e  mov     r9d, 1; unsigned int
0x38388fd24  lea     r8, [rsp+2C0h+var_258]; HKEY *
0x38388fd29  mov     rdx, r15; char *
0x38388fd2c  lea     rcx, [rsp+2C0h+var_27C]; this
0x38388fd31  call    ?CSgetSNISubRegKey@NLregC@@AEAAJPEBDPEAPEAUHKEY__@@KH@Z; NLregC::CSgetSNISubRegKey(char const *,HKEY__ * *,ulong,int)
0x38388fd36  mov     ebx, eax
0x38388fd38  test    eax, eax
0x38388fd3a  jnz     short loc_38388FD8D
0x38388fd3c  xor     edx, edx; Val
0x38388fd3e  mov     r8d, 204h; Size
0x38388fd44  lea     rcx, [rbp+1C0h+var_240]; void *
0x38388fd48  call    memset
0x38388fd4d  mov     [rbp+1C0h+var_140], esi
0x38388fd53  lea     rax, [rsp+2C0h+var_260]
0x38388fd58  mov     [rsp+2C0h+var_290], rax
0x38388fd5d  lea     rax, [rbp+1C0h+var_13C]
0x38388fd64  mov     qword ptr [rsp+2C0h+cchCount2], rax
0x38388fd69  lea     rax, [rbp+1C0h+var_140]
0x38388fd70  mov     [rsp+2C0h+lpString2], rax
0x38388fd75  lea     r9, [rbp+1C0h+var_240]
0x38388fd79  mov     edx, 1
0x38388fd7e  mov     r8d, edx
0x38388fd81  mov     rcx, [rsp+2C0h+var_258]
0x38388fd86  call    ?CSgetFlagOrProperty@NLregC@@AEAAJPEAUHKEY__@@W4CSFPVTYPE@@KPEADKPEAKPEAE3@Z; NLregC::CSgetFlagOrProperty(HKEY__ *,CSFPVTYPE,ulong,char *,ulong,ulong *,uchar *,ulong *)
0x38388fd8b  mov     ebx, eax
0x38388fd8d  mov     rcx, [rsp+2C0h+var_258]; lpMem
0x38388fd92  test    rcx, rcx
0x38388fd95  jz      short loc_38388FD9C
0x38388fd97  call    IniRegCloseKey
0x38388fd9c  test    ebx, ebx
0x38388fd9e  jnz     loc_3839020C8
0x38388fda4  cmp     [rbp+1C0h+var_140], 1
0x38388fdab  jnz     loc_3839020C8
0x38388fdb1  mov     rcx, rdi
0x38388fdb4  mov     rax, r14
0x38388fdb7  nop     word ptr [rax+rax+00000000h]
0x38388fdc0  cmp     [rax], sil
0x38388fdc3  jz      short loc_38388FDDB
0x38388fdc5  inc     rax
0x38388fdc8  dec     rcx
0x38388fdcb  jnz     short loc_38388FDC0
0x38388fdcd  jmp     loc_3839020B4
0x38388fddb  test    rcx, rcx
0x38388fdde  jz      loc_383902152
0x38388fde4  mov     rdx, rdi
0x38388fde7  sub     rdx, rcx
0x38388fdea  sub     rdi, rdx
0x38388fded  lea     rax, [r14+rdx]
0x38388fdf1  jz      loc_3839020BB
0x38388fdf7  lea     rcx, [rdx+7FFFFEFAh]
0x38388fdfe  add     rcx, rdi
0x38388fe01  lea     r8, [rbp+1C0h+var_13C]
0x38388fe08  sub     r8, rax
0x38388fe0b  nop     dword ptr [rax+rax+00h]
0x38388fe10  test    rcx, rcx
0x38388fe13  jz      short loc_38388FE30
0x38388fe15  movzx   edx, byte ptr [rax+r8]
0x38388fe1a  test    dl, dl
0x38388fe1c  jz      short loc_38388FE30
0x38388fe1e  mov     [rax], dl
0x38388fe20  inc     rax
0x38388fe23  dec     rcx
0x38388fe26  dec     rdi
0x38388fe29  jnz     short loc_38388FE10
0x38388fe2b  jmp     loc_3839020B9
0x38388fe30  test    rdi, rdi
0x38388fe33  jz      loc_3839020BB
0x38388fe39  mov     byte ptr [rax], 0
0x38388fe3c  test    esi, esi
0x38388fe3e  jmp     loc_38388FBF3
0x383901f99  mov     rax, cs:off_383B48A88; "<GetProtocolDefaults|API|SNI> pProtElem"...
0x383901fa0  test    rax, rax
0x383901fa3  jz      loc_383884A11
0x383901fa9  mov     [rsp+2C0h+lpString2], rbx
0x383901fae  mov     r9, rdx
0x383901fb1  mov     r8, rcx
0x383901fb4  mov     rdx, cs:off_383B48A88; "<GetProtocolDefaults|API|SNI> pProtElem"...
0x383901fbb  lea     rcx, [rsp+2C0h+var_278]
0x383901fc0  call    _bidScopeEnterA
0x383901fc5  nop
0x383901fc6  jmp     loc_383884A11
0x383901fcb  test    byte ptr cs:_bidGblFlags, 2
0x383901fd2  jz      loc_383902152
0x383901fd8  mov     rax, cs:off_383B477D8; "<GetProtocolDefaults|ERR|SNI> providerN"...
0x383901fdf  test    rax, rax
0x383901fe2  jz      loc_383902152
0x383901fe8  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383901ff0  jz      loc_383902152
0x383901ff6  mov     [rsp+2C0h+lpString2], rsi
0x383901ffb  mov     r9, cs:off_383B477D8; "<GetProtocolDefaults|ERR|SNI> providerN"...
0x383902002  mov     r8d, 0EE400h
0x383902008  mov     rdx, cs:off_383B45158; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x38390200f  mov     rcx, cs:_bidID
0x383902016  call    cs:off_383B15038
0x38390201c  jmp     loc_383902152
0x383902021  lea     rcx, [r14+208h]
0x383902028  lea     rdx, a1433; "1433"
0x38390202f  sub     rdx, rcx
0x383902032  nop     dword ptr [rax+00000000h]
0x383902039  nop     dword ptr [rax+00000000h]
0x383902040  lea     rax, [rbx+7FFFFEFEh]
0x383902047  test    rax, rax
  ... truncated ...
```
