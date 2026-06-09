# ConnectUsingCache(ConnectParameter *,ProtList *,SNI_CLIENT_CONSUMER_INFO *,SNI_Conn * *,int)

- ea: `0x383ad7860`
- end: `0x383ad7cda`
- name: `?ConnectUsingCache@@YA_NPEAVConnectParameter@@PEAVProtList@@PEAUSNI_CLIENT_CONSUMER_INFO@@PEAPEAVSNI_Conn@@H@Z`
- size: `1146`
- prototype: `bool __usercall@<al>(struct ConnectParameter *@<rcx>, struct ProtList *@<rdx>, struct SNI_CLIENT_CONSUMER_INFO *@<r8>, struct SNI_Conn **@<r9>, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x383883ac0`

## callees

- `0x3838434c0`
- `0x383880090`
- `0x3838810e0`
- `0x38388ed90`
- `0x38391ac00`
- `0x38391ac40`
- `0x38391ae80`
- `0x38391af20`
- `0x383ac1670`
- `0x383ac17d0`
- `0x383ad7860`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x383ad7916`
- `KERNEL32!GetTickCount` at `0x383ad7b69`
- `KERNEL32!GetTickCount` at `0x383ad7916`
- `KERNEL32!GetTickCount` at `0x383ad7b69`
- `KERNEL32!CompareStringA` at `0x383ad7a8b`
- `KERNEL32!CompareStringA` at `0x383ad7a8b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ConnectUsingCache(
        struct ConnectParameter *a1,
        struct ProtList *a2,
        struct SNI_CLIENT_CONSUMER_INFO *a3,
        struct SNI_Conn **a4,
        unsigned int a5)
{
  unsigned int v9; // ebx
  DWORD TickCount; // r13d
  struct ProtElem *v11; // r8
  const CHAR *v13; // r8
  const char *v14; // rdx
  const char *v15; // rdx
  _QWORD v16[2]; // [rsp+40h] [rbp-C0h] BYREF
  char v17[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v18; // [rsp+54h] [rbp-ACh]
  char v19; // [rsp+58h] [rbp-A8h]
  char v20; // [rsp+158h] [rbp+58h]
  __int64 v21; // [rsp+458h] [rbp+358h]

  v16[1] = -2;
  v16[0] = -1;
  v9 = a5;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_383B48E58[0] )
    bidScopeEnterA(v16, off_383B48E58[0], a1);
  *(_DWORD *)v17 = 9;
  v18 = 9;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  TickCount = GetTickCount();
  if ( ProtElem::Init((ProtElem *)v17, (const char *const)a1, (const char *const)a1 + 256) )
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B48280[0] && bidID != -1 )
      off_383B15038();
LABEL_9:
    if ( v16[0] != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
      off_383B15058();
    return 0;
  }
  if ( !(unsigned int)LastConnectCache::GetEntry((PCNZCH)a1 + 1035, v17, v11) )
  {
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B48278[0] && bidID != -1 )
      off_383B15038();
    goto LABEL_9;
  }
  if ( *((_BYTE *)a1 + 768) )
  {
    if ( *(_DWORD *)v17 )
    {
      switch ( *(_DWORD *)v17 )
      {
        case 1:
          v13 = "np";
          break;
        case 4:
          v13 = "lpc";
          break;
        case 7:
          v13 = "tcp";
          break;
        default:
LABEL_30:
          if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B48270[0] && bidID != -1 )
            off_383B15038();
          goto LABEL_9;
      }
    }
    else
    {
      v13 = "http";
    }
    if ( CompareStringA(0x800u, 0x20000u, v13, -1, (PCNZCH)a1 + 768, -1) != 2 )
      goto LABEL_30;
  }
  else if ( !ProtList::Find(a2, *(unsigned int *)v17) )
  {
    LastConnectCache::RemoveEntry((LPCSTR)a1 + 1035, v14);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B48268[0] && bidID != -1 )
      off_383B15038();
    goto LABEL_9;
  }
  if ( a5 != -1 )
  {
    v9 = TickCount + a5 - GetTickCount();
    if ( v9 == -1 )
      v9 = -2;
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B48260[0] )
      bidTraceA(off_383B45BF8[0], 474112, off_383B48260[0], v9);
  }
  if ( Connect(a1, a3, (struct ProtElem *)v17, a4, v9) )
  {
    LastConnectCache::RemoveEntry((LPCSTR)a1 + 1035, v15);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B48258[0] && bidID != -1 )
      off_383B15038();
    goto LABEL_9;
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B48250[0] && bidID != -1 )
    off_383B15038();
  if ( v16[0] != -1 && (bidGblFlags & 4) != 0 && bidID != -1 )
    off_383B15058();
  return 1;
}

```

## disassembly

```asm
0x383ad7860  push    rbp
0x383ad7862  push    rbx
0x383ad7863  push    rsi
0x383ad7864  push    rdi
0x383ad7865  push    r12
0x383ad7867  push    r13
0x383ad7869  push    r14
0x383ad786b  push    r15
0x383ad786d  lea     rbp, [rsp-378h]
0x383ad7875  sub     rsp, 478h
0x383ad787c  mov     [rsp+4B0h+var_468], 0FFFFFFFFFFFFFFFEh
0x383ad7885  mov     rax, cs:__security_cookie
0x383ad788c  xor     rax, rsp
0x383ad788f  mov     [rbp+3B0h+var_50], rax
0x383ad7896  mov     r12, r9
0x383ad7899  mov     r15, r8
0x383ad789c  mov     r14, rdx
0x383ad789f  mov     rdi, rcx
0x383ad78a2  mov     [rsp+4B0h+var_470], 0FFFFFFFFFFFFFFFFh
0x383ad78ab  mov     eax, cs:_bidGblFlags
0x383ad78b1  and     eax, 20004h
0x383ad78b6  mov     ebx, [rbp+3B0h+arg_20]
0x383ad78bc  cmp     eax, 20004h
0x383ad78c1  jnz     short loc_383AD78F4
0x383ad78c3  mov     rax, cs:off_383B48E58; "<ConnectUsingCache|API|SNI> pConnectPar"...
0x383ad78ca  test    rax, rax
0x383ad78cd  jz      short loc_383AD78F4
0x383ad78cf  mov     [rsp+4B0h+var_480], ebx
0x383ad78d3  mov     qword ptr [rsp+4B0h+cchCount2], r9
0x383ad78d8  mov     [rsp+4B0h+lpString2], r8
0x383ad78dd  mov     r9, rdx
0x383ad78e0  mov     r8, rcx
0x383ad78e3  mov     rdx, cs:off_383B48E58; "<ConnectUsingCache|API|SNI> pConnectPar"...
0x383ad78ea  lea     rcx, [rsp+4B0h+var_470]
0x383ad78ef  call    _bidScopeEnterA
0x383ad78f4  mov     dword ptr [rsp+4B0h+var_460], 9
0x383ad78fc  mov     [rsp+4B0h+var_45C], 9
0x383ad7904  mov     [rsp+4B0h+var_458], 0
0x383ad7909  mov     [rbp+3B0h+var_358], 0
0x383ad790d  xor     esi, esi
0x383ad790f  mov     [rbp+3B0h+var_58], rsi
0x383ad7916  call    cs:__imp_GetTickCount
0x383ad791c  mov     r13d, eax
0x383ad791f  lea     r8, [rdi+100h]; char *
0x383ad7926  mov     rdx, rdi; char *
0x383ad7929  lea     rcx, [rsp+4B0h+var_460]; this
0x383ad792e  call    ?Init@ProtElem@@QEAAKQEBD0@Z; ProtElem::Init(char const * const,char const * const)
0x383ad7933  test    eax, eax
0x383ad7935  jz      loc_383AD79BF
0x383ad793b  mov     eax, cs:_bidGblFlags
0x383ad7941  and     eax, 20002h
0x383ad7946  cmp     eax, 20002h
0x383ad794b  jnz     short loc_383AD798A
0x383ad794d  mov     rax, cs:off_383B48280; "<ConnectUsingCache|RET|SNI> false\n"
0x383ad7954  test    rax, rax
0x383ad7957  jz      short loc_383AD798A
0x383ad7959  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ad7961  jz      short loc_383AD798A
0x383ad7963  mov     [rsp+4B0h+lpString2], rsi
0x383ad7968  mov     r9, cs:off_383B48280; "<ConnectUsingCache|RET|SNI> false\n"
0x383ad796f  mov     r8d, 61400h
0x383ad7975  mov     rdx, cs:off_383B45C18; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ad797c  mov     rcx, cs:_bidID
0x383ad7983  call    cs:off_383B15038
0x383ad7989  nop
0x383ad798a  cmp     [rsp+4B0h+var_470], 0FFFFFFFFFFFFFFFFh
0x383ad7990  jz      short loc_383AD79B8
0x383ad7992  test    byte ptr cs:_bidGblFlags, 4
0x383ad7999  jz      short loc_383AD79B8
0x383ad799b  mov     rcx, cs:_bidID
0x383ad79a2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383ad79a6  jz      short loc_383AD79B8
0x383ad79a8  lea     r9, [rsp+4B0h+var_470]
0x383ad79ad  xor     r8d, r8d
0x383ad79b0  xor     edx, edx
0x383ad79b2  call    cs:off_383B15058
0x383ad79b8  xor     al, al
0x383ad79ba  jmp     loc_383AD7CB7
0x383ad79bf  lea     rdx, [rsp+4B0h+var_460]; char *
0x383ad79c4  lea     rcx, [rdi+40Bh]; lpString2
0x383ad79cb  call    ?GetEntry@LastConnectCache@@YAHPEBDPEAVProtElem@@@Z; LastConnectCache::GetEntry(char const *,ProtElem *)
0x383ad79d0  test    eax, eax
0x383ad79d2  jnz     short loc_383AD7A28
0x383ad79d4  mov     eax, cs:_bidGblFlags
0x383ad79da  and     eax, 20002h
0x383ad79df  cmp     eax, 20002h
0x383ad79e4  jnz     short loc_383AD7A23
0x383ad79e6  mov     rax, cs:off_383B48278; "<ConnectUsingCache|RET|SNI> false\n"
0x383ad79ed  test    rax, rax
0x383ad79f0  jz      short loc_383AD7A23
0x383ad79f2  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ad79fa  jz      short loc_383AD7A23
0x383ad79fc  mov     [rsp+4B0h+lpString2], rsi
0x383ad7a01  mov     r9, cs:off_383B48278; "<ConnectUsingCache|RET|SNI> false\n"
0x383ad7a08  mov     r8d, 63800h
0x383ad7a0e  mov     rdx, cs:off_383B45C10; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ad7a15  mov     rcx, cs:_bidID
0x383ad7a1c  call    cs:off_383B15038
0x383ad7a22  nop
0x383ad7a23  jmp     loc_383AD798A
0x383ad7a28  lea     rdx, [rdi+300h]
0x383ad7a2f  cmp     [rdx], sil
0x383ad7a32  jz      loc_383AD7AEE
0x383ad7a38  mov     ecx, dword ptr [rsp+4B0h+var_460]
0x383ad7a3c  test    ecx, ecx
0x383ad7a3e  jz      short loc_383AD7A69
0x383ad7a40  dec     ecx
0x383ad7a42  jz      short loc_383AD7A60
0x383ad7a44  sub     ecx, 3
0x383ad7a47  jz      short loc_383AD7A57
0x383ad7a49  cmp     ecx, 3
0x383ad7a4c  jnz     short loc_383AD7A9A
0x383ad7a4e  lea     r8, aTcp; "tcp"
0x383ad7a55  jmp     short loc_383AD7A70
0x383ad7a57  lea     r8, aLpc; "lpc"
0x383ad7a5e  jmp     short loc_383AD7A70
0x383ad7a60  lea     r8, aNp; "np"
0x383ad7a67  jmp     short loc_383AD7A70
0x383ad7a69  lea     r8, aHttp; "http"
0x383ad7a70  mov     [rsp+4B0h+cchCount2], 0FFFFFFFFh; cchCount2
0x383ad7a78  mov     [rsp+4B0h+lpString2], rdx; lpString2
0x383ad7a7d  or      r9d, 0FFFFFFFFh; cchCount1
0x383ad7a81  mov     edx, 20000h; dwCmpFlags
0x383ad7a86  mov     ecx, 800h; Locale
0x383ad7a8b  call    cs:__imp_CompareStringA
0x383ad7a91  cmp     eax, 2
0x383ad7a94  jz      loc_383AD7B64
0x383ad7a9a  mov     eax, cs:_bidGblFlags
0x383ad7aa0  and     eax, 20002h
0x383ad7aa5  cmp     eax, 20002h
0x383ad7aaa  jnz     short loc_383AD7AE9
0x383ad7aac  mov     rax, cs:off_383B48270; "<ConnectUsingCache|RET|SNI> false\n"
0x383ad7ab3  test    rax, rax
0x383ad7ab6  jz      short loc_383AD7AE9
0x383ad7ab8  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ad7ac0  jz      short loc_383AD7AE9
0x383ad7ac2  mov     [rsp+4B0h+lpString2], rsi
0x383ad7ac7  mov     r9, cs:off_383B48270; "<ConnectUsingCache|RET|SNI> false\n"
0x383ad7ace  mov     r8d, 6EC00h
0x383ad7ad4  mov     rdx, cs:off_383B45C08; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ad7adb  mov     rcx, cs:_bidID
0x383ad7ae2  call    cs:off_383B15038
0x383ad7ae8  nop
0x383ad7ae9  jmp     loc_383AD798A
0x383ad7aee  mov     edx, dword ptr [rsp+4B0h+var_460]
0x383ad7af2  mov     rcx, r14
0x383ad7af5  call    ?Find@ProtList@@QEAAPEAVProtElem@@W4ProviderNum@@@Z; ProtList::Find(ProviderNum)
0x383ad7afa  test    rax, rax
0x383ad7afd  jnz     short loc_383AD7B64
0x383ad7aff  lea     rcx, [rdi+40Bh]; lpValueName
0x383ad7b06  call    ?RemoveEntry@LastConnectCache@@YAXPEBD@Z; LastConnectCache::RemoveEntry(char const *)
0x383ad7b0b  mov     r11d, cs:_bidGblFlags
0x383ad7b12  and     r11d, 20002h
0x383ad7b19  cmp     r11d, 20002h
0x383ad7b20  jnz     short loc_383AD7B5F
0x383ad7b22  mov     rax, cs:off_383B48268; "<ConnectUsingCache|RET|SNI> false\n"
0x383ad7b29  test    rax, rax
0x383ad7b2c  jz      short loc_383AD7B5F
0x383ad7b2e  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ad7b36  jz      short loc_383AD7B5F
0x383ad7b38  mov     [rsp+4B0h+lpString2], rsi
0x383ad7b3d  mov     r9, cs:off_383B48268; "<ConnectUsingCache|RET|SNI> false\n"
0x383ad7b44  mov     r8d, 71000h
0x383ad7b4a  mov     rdx, cs:off_383B45C00; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ad7b51  mov     rcx, cs:_bidID
0x383ad7b58  call    cs:off_383B15038
0x383ad7b5e  nop
0x383ad7b5f  jmp     loc_383AD798A
0x383ad7b64  cmp     ebx, 0FFFFFFFFh
0x383ad7b67  jz      short loc_383AD7BB8
0x383ad7b69  call    cs:__imp_GetTickCount
0x383ad7b6f  add     ebx, r13d
0x383ad7b72  sub     ebx, eax
0x383ad7b74  mov     eax, 0FFFFFFFEh
0x383ad7b79  cmp     ebx, 0FFFFFFFFh
0x383ad7b7c  cmovz   ebx, eax
0x383ad7b7f  mov     eax, cs:_bidGblFlags
0x383ad7b85  and     eax, 20002h
0x383ad7b8a  cmp     eax, 20002h
0x383ad7b8f  jnz     short loc_383AD7BB8
0x383ad7b91  mov     rax, cs:off_383B48260; "<ConnectUsingCache|SNI> timeout: %d\n"
0x383ad7b98  test    rax, rax
0x383ad7b9b  jz      short loc_383AD7BB8
0x383ad7b9d  mov     r9d, ebx
0x383ad7ba0  mov     r8, cs:off_383B48260; "<ConnectUsingCache|SNI> timeout: %d\n"
0x383ad7ba7  mov     edx, 73C00h
0x383ad7bac  mov     rcx, cs:off_383B45BF8; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ad7bb3  call    _bidTraceA
0x383ad7bb8  mov     dword ptr [rsp+4B0h+lpString2], ebx; int
0x383ad7bbc  mov     r9, r12; struct SNI_Conn **
0x383ad7bbf  lea     r8, [rsp+4B0h+var_460]; struct ProtElem *
0x383ad7bc4  mov     rdx, r15; struct SNI_CLIENT_CONSUMER_INFO *
0x383ad7bc7  mov     rcx, rdi; struct ConnectParameter *
0x383ad7bca  call    ?Connect@@YAKPEAVConnectParameter@@PEAUSNI_CLIENT_CONSUMER_INFO@@PEAVProtElem@@PEAPEAVSNI_Conn@@H@Z; Connect(ConnectParameter *,SNI_CLIENT_CONSUMER_INFO *,ProtElem *,SNI_Conn * *,int)
0x383ad7bcf  test    eax, eax
0x383ad7bd1  jz      short loc_383AD7C38
0x383ad7bd3  lea     rcx, [rdi+40Bh]; lpValueName
0x383ad7bda  call    ?RemoveEntry@LastConnectCache@@YAXPEBD@Z; LastConnectCache::RemoveEntry(char const *)
0x383ad7bdf  mov     r11d, cs:_bidGblFlags
0x383ad7be6  and     r11d, 20002h
0x383ad7bed  cmp     r11d, 20002h
0x383ad7bf4  jnz     short loc_383AD7C33
0x383ad7bf6  mov     rax, cs:off_383B48258; "<ConnectUsingCache|RET|SNI> false\n"
0x383ad7bfd  test    rax, rax
0x383ad7c00  jz      short loc_383AD7C33
0x383ad7c02  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ad7c0a  jz      short loc_383AD7C33
0x383ad7c0c  mov     [rsp+4B0h+lpString2], rsi
0x383ad7c11  mov     r9, cs:off_383B48258; "<ConnectUsingCache|RET|SNI> false\n"
0x383ad7c18  mov     r8d, 75800h
0x383ad7c1e  mov     rdx, cs:off_383B45BF0; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ad7c25  mov     rcx, cs:_bidID
0x383ad7c2c  call    cs:off_383B15038
0x383ad7c32  nop
0x383ad7c33  jmp     loc_383AD798A
0x383ad7c38  mov     eax, cs:_bidGblFlags
0x383ad7c3e  and     eax, 20002h
0x383ad7c43  cmp     eax, 20002h
0x383ad7c48  jnz     short loc_383AD7C87
0x383ad7c4a  mov     rax, cs:off_383B48250; "<ConnectUsingCache|RET|SNI> true\n"
0x383ad7c51  test    rax, rax
0x383ad7c54  jz      short loc_383AD7C87
0x383ad7c56  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ad7c5e  jz      short loc_383AD7C87
0x383ad7c60  mov     [rsp+4B0h+lpString2], rsi
0x383ad7c65  mov     r9, cs:off_383B48250; "<ConnectUsingCache|RET|SNI> true\n"
0x383ad7c6c  mov     r8d, 76C00h
0x383ad7c72  mov     rdx, cs:off_383B45BE8; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ad7c79  mov     rcx, cs:_bidID
0x383ad7c80  call    cs:off_383B15038
0x383ad7c86  nop
0x383ad7c87  cmp     [rsp+4B0h+var_470], 0FFFFFFFFFFFFFFFFh
0x383ad7c8d  jz      short loc_383AD7CB5
0x383ad7c8f  test    byte ptr cs:_bidGblFlags, 4
0x383ad7c96  jz      short loc_383AD7CB5
0x383ad7c98  mov     rcx, cs:_bidID
0x383ad7c9f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x383ad7ca3  jz      short loc_383AD7CB5
0x383ad7ca5  lea     r9, [rsp+4B0h+var_470]
0x383ad7caa  xor     r8d, r8d
0x383ad7cad  xor     edx, edx
0x383ad7caf  call    cs:off_383B15058
0x383ad7cb5  mov     al, 1
0x383ad7cb7  mov     rcx, [rbp+3B0h+var_50]
0x383ad7cbe  xor     rcx, rsp; StackCookie
0x383ad7cc1  call    __security_check_cookie
0x383ad7cc6  add     rsp, 478h
0x383ad7ccd  pop     r15
0x383ad7ccf  pop     r14
0x383ad7cd1  pop     r13
0x383ad7cd3  pop     r12
0x383ad7cd5  pop     rdi
0x383ad7cd6  pop     rsi
0x383ad7cd7  pop     rbx
0x383ad7cd8  pop     rbp
0x383ad7cd9  retn
```
