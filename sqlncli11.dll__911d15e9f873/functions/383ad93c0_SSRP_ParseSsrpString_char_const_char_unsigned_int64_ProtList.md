# SSRP::ParseSsrpString(char const *,char *,unsigned __int64,ProtList *)

- ea: `0x383ad93c0`
- end: `0x383ad983a`
- name: `?ParseSsrpString@SSRP@@YAKPEBDPEAD_KPEAVProtList@@@Z`
- size: `1146`
- prototype: `unsigned int __fastcall(PCNZCH lpString2, LPCSTR lpCurrentChar, char *, unsigned __int64, struct ProtList *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x383ad9860`

## callees

- `0x3838434c0`
- `0x383884870`
- `0x383884bb0`
- `0x38388ed90`
- `0x38391ac00`
- `0x383ab00c0`
- `0x383ab05b0`
- `0x383ac48c0`
- `0x383ad93c0`
- `0x383adb6a0`

## import_xrefs

- `MSVCR100!free` at `0x383ad945c`
- `MSVCR100!free` at `0x383ad97b9`
- `MSVCR100!free` at `0x383ad945c`
- `MSVCR100!free` at `0x383ad97b9`
- `MSVCR100!strchr` at `0x383ad94fa`
- `MSVCR100!strchr` at `0x383ad9531`
- `MSVCR100!strchr` at `0x383ad9551`
- `MSVCR100!strchr` at `0x383ad94fa`
- `MSVCR100!strchr` at `0x383ad9531`
- `MSVCR100!strchr` at `0x383ad9551`
- `MSVCR100!_dupenv_s` at `0x383ad9628`
- `MSVCR100!_dupenv_s` at `0x383ad9628`
- `KERNEL32!CompareStringA` at `0x383ad965b`
- `KERNEL32!CompareStringA` at `0x383ad965b`

## pseudocode

```c
__int64 __fastcall SSRP::ParseSsrpString(PCNZCH lpString2, LPCSTR lpCurrentChar, char *a3, int **a4)
{
  unsigned int v6; // ebp
  __int64 v8; // rax
  char *v9; // rax
  const char *v10; // rdi
  _DWORD *v11; // r15
  char *v12; // rax
  char *v13; // rbx
  char *v14; // rax
  char *v15; // rsi
  __int64 v16; // rdi
  char v17; // cl
  const char *v18; // rbx
  bool v19; // sf
  __int64 v20; // rdi
  _BYTE *v21; // rcx
  __int64 v22; // rdx
  int v23; // r8d
  char *v24; // rbx
  char v25; // al
  int *v26; // rdi
  __int64 v27; // rbx
  __int64 i; // rax
  int v29; // edx
  ProtElem *v30; // rax
  unsigned int v31; // edx
  int v32; // ecx
  void *Block; // [rsp+30h] [rbp-88h] BYREF
  _DWORD v34[10]; // [rsp+38h] [rbp-80h] BYREF

  v6 = 0;
  Block = 0;
  if ( (unsigned __int64)a3 > 0x7FFFFFFF )
  {
    if ( (bidGblFlags & 0x20002) != 0x20002 || !off_383B48428[0] || bidID == -1 )
    {
LABEL_8:
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B48410[0] && bidID != -1 )
        off_383B15038();
      return 0xFFFFFFFFLL;
    }
    off_383B15038();
LABEL_6:
    if ( Block )
      free(Block);
    goto LABEL_8;
  }
  v8 = StrStrA_SYS(lpCurrentChar);
  if ( !v8 )
    goto LABEL_6;
  v9 = strchr((const char *)(v8 + 8), 59);
  if ( !v9 )
    goto LABEL_6;
  v10 = v9 + 1;
  if ( v9[1] != 59 )
  {
    v11 = v34;
    while ( v6 < 0xA )
    {
      v12 = strchr(v10, 59);
      if ( !v12 )
        break;
      v13 = v12 + 1;
      *v12 = 0;
      v14 = strchr(v12 + 1, 59);
      v15 = v14;
      if ( !v14 )
        break;
      *v14 = 0;
      if ( (int)v14 - (int)v13 > 255 )
        break;
      switch ( *v10 )
      {
        case 'a':
        case 'b':
        case 'r':
        case 's':
        case 'v':
          goto LABEL_45;
        case 'n':
          v16 = ProtList::Find(a4, 1);
          if ( !v16 )
            goto LABEL_45;
          *v11++ = 1;
          ++v6;
          if ( *v13 != 92 )
            goto LABEL_6;
          if ( v13[1] != 92 )
            goto LABEL_6;
          v17 = v13[2];
          v18 = v13 + 2;
          if ( !v17 )
            goto LABEL_6;
          while ( v17 != 92 )
          {
            v17 = *++v18;
            if ( !v17 )
              goto LABEL_6;
          }
          if ( !*v18 )
            goto LABEL_6;
          if ( !IsLocalHost(lpString2) )
            goto LABEL_35;
          if ( _dupenv_s((char **)&Block, 0, "_CLUSTER_NETWORK_NAME_") )
            goto LABEL_6;
          if ( Block && CompareStringA(0x800u, 0x20001u, (PCNZCH)Block, -1, lpString2, -1) == 2 )
          {
LABEL_35:
            *(_BYTE *)(v16 + 775) = 0;
            v19 = (int)StringCchPrintfA((char *)(v16 + 520), 0x105u, "\\\\%s%s", lpString2, v18) < 0;
          }
          else
          {
            *(_BYTE *)(v16 + 775) = 0;
            v19 = (int)StringCchPrintfA((char *)(v16 + 520), 0x105u, "\\\\.%s", v18) < 0;
          }
          goto LABEL_44;
        case 't':
          v20 = ProtList::Find(a4, 7);
          if ( !v20 )
            goto LABEL_45;
          *v11 = 7;
          ++v6;
          ++v11;
          if ( !(unsigned int)Strtoi(v13) )
            goto LABEL_6;
          v21 = (_BYTE *)(v20 + 520);
          v22 = 256;
          v23 = 0;
          v24 = &v13[-v20 - 520];
          break;
        default:
          goto LABEL_6;
      }
      while ( v22 != -2147483390 )
      {
        v25 = v21[(_QWORD)v24];
        if ( !v25 )
          break;
        *v21++ = v25;
        if ( !--v22 )
        {
          --v21;
          v23 = -2147024774;
          break;
        }
      }
      *v21 = 0;
      v19 = v23 < 0;
LABEL_44:
      if ( v19 )
        break;
LABEL_45:
      v10 = v15 + 1;
      if ( v15[1] == 59 )
        goto LABEL_46;
    }
    goto LABEL_6;
  }
LABEL_46:
  v26 = *a4;
  v27 = (int)v6;
  while ( v26 )
  {
    for ( i = 0; i < v27; ++i )
    {
      if ( v34[i] == *v26 )
        break;
    }
    if ( i == v27 )
    {
      v29 = *v26;
      v26 = (int *)*((_QWORD *)v26 + 129);
      if ( v29 != 4 )
      {
        v30 = (ProtElem *)ProtList::RemoveProt(a4);
        if ( v30 )
          ProtElem::`scalar deleting destructor'(v30, v31);
      }
    }
    else
    {
      v32 = v34[v27 - 1];
      v26 = (int *)*((_QWORD *)v26 + 129);
      --v27;
      v34[i] = v32;
    }
  }
  if ( Block )
    free(Block);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_383B48418[0] && bidID != -1 )
    off_383B15038();
  return 0;
}

```

## disassembly

```asm
0x383ad93c0  push    rbx
0x383ad93c2  push    rbp
0x383ad93c3  push    rsi
0x383ad93c4  push    rdi
0x383ad93c5  push    r12
0x383ad93c7  push    r13
0x383ad93c9  push    r14
0x383ad93cb  push    r15
0x383ad93cd  sub     rsp, 78h
0x383ad93d1  mov     rax, cs:__security_cookie
0x383ad93d8  xor     rax, rsp
0x383ad93db  mov     [rsp+0B8h+var_58], rax
0x383ad93e0  xor     r13d, r13d
0x383ad93e3  mov     r14, r9
0x383ad93e6  mov     rax, r8
0x383ad93e9  mov     r10, rdx
0x383ad93ec  mov     r12, rcx
0x383ad93ef  mov     ebp, r13d
0x383ad93f2  mov     [rsp+0B8h+Block], r13
0x383ad93f7  cmp     r8, 7FFFFFFFh
0x383ad93fe  jbe     loc_383AD94D1
0x383ad9404  mov     eax, cs:_bidGblFlags
0x383ad940a  and     eax, 20002h
0x383ad940f  cmp     eax, 20002h
0x383ad9414  jnz     short loc_383AD9462
0x383ad9416  mov     rax, cs:off_383B48428; "<SSRP::ParseSsrpString|SNI> String leng"...
0x383ad941d  test    rax, rax
0x383ad9420  jz      short loc_383AD9462
0x383ad9422  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ad942a  jz      short loc_383AD9462
0x383ad942c  mov     r9, cs:off_383B48428; "<SSRP::ParseSsrpString|SNI> String leng"...
0x383ad9433  mov     rdx, cs:off_383B45DC0; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ad943a  mov     rcx, cs:_bidID
0x383ad9441  mov     r8d, 93400h
0x383ad9447  mov     [rsp+0B8h+lpString2], r13
0x383ad944c  call    cs:off_383B15038
0x383ad9452  mov     rcx, [rsp+0B8h+Block]; jumptable 0000000383AD95A1 default case, cases 99-109,111-113,117
0x383ad9457  test    rcx, rcx
0x383ad945a  jz      short loc_383AD9462
0x383ad945c  call    cs:__imp_free
0x383ad9462  mov     eax, cs:_bidGblFlags
0x383ad9468  and     eax, 20002h
0x383ad946d  cmp     eax, 20002h
0x383ad9472  jnz     short loc_383AD94B0
0x383ad9474  mov     rax, cs:off_383B48410; "<SSRP::ParseSsrpString|RET|SNI> fail\n"
0x383ad947b  test    rax, rax
0x383ad947e  jz      short loc_383AD94B0
0x383ad9480  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ad9488  jz      short loc_383AD94B0
0x383ad948a  mov     r9, cs:off_383B48410; "<SSRP::ParseSsrpString|RET|SNI> fail\n"
0x383ad9491  mov     rdx, cs:off_383B45DA8; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ad9498  mov     rcx, cs:_bidID
0x383ad949f  mov     r8d, 0CFC00h
0x383ad94a5  mov     [rsp+0B8h+lpString2], r13
0x383ad94aa  call    cs:off_383B15038
0x383ad94b0  or      eax, 0FFFFFFFFh
0x383ad94b3  mov     rcx, [rsp+0B8h+var_58]
0x383ad94b8  xor     rcx, rsp; StackCookie
0x383ad94bb  call    __security_check_cookie
0x383ad94c0  add     rsp, 78h
0x383ad94c4  pop     r15
0x383ad94c6  pop     r14
0x383ad94c8  pop     r13
0x383ad94ca  pop     r12
0x383ad94cc  pop     rdi
0x383ad94cd  pop     rsi
0x383ad94ce  pop     rbp
0x383ad94cf  pop     rbx
0x383ad94d0  retn
0x383ad94d1  lea     r8, aVersion; "Version;"
0x383ad94d8  mov     r9d, 8
0x383ad94de  mov     edx, eax
0x383ad94e0  mov     rcx, r10; lpCurrentChar
0x383ad94e3  call    StrStrA_SYS
0x383ad94e8  test    rax, rax
0x383ad94eb  jz      def_383AD95A1; jumptable 0000000383AD95A1 default case, cases 99-109,111-113,117
0x383ad94f1  lea     rcx, [rax+8]; Str
0x383ad94f5  mov     edx, 3Bh ; ';'; Val
0x383ad94fa  call    cs:__imp_strchr
0x383ad9500  mov     rdi, rax
0x383ad9503  test    rax, rax
0x383ad9506  jz      def_383AD95A1; jumptable 0000000383AD95A1 default case, cases 99-109,111-113,117
0x383ad950c  inc     rdi
0x383ad950f  cmp     byte ptr [rdi], 3Bh ; ';'
0x383ad9512  jz      loc_383AD9748
0x383ad9518  lea     r15, [rsp+0B8h+var_80]
0x383ad951d  nop     dword ptr [rax]
0x383ad9520  cmp     ebp, 0Ah
0x383ad9523  jnb     def_383AD95A1; jumptable 0000000383AD95A1 default case, cases 99-109,111-113,117
0x383ad9529  mov     edx, 3Bh ; ';'; Val
0x383ad952e  mov     rcx, rdi; Str
0x383ad9531  call    cs:__imp_strchr
0x383ad9537  mov     rbx, rax
0x383ad953a  test    rax, rax
0x383ad953d  jz      def_383AD95A1; jumptable 0000000383AD95A1 default case, cases 99-109,111-113,117
0x383ad9543  inc     rbx
0x383ad9546  mov     edx, 3Bh ; ';'; Val
0x383ad954b  mov     [rax], r13b
0x383ad954e  mov     rcx, rbx; Str
0x383ad9551  call    cs:__imp_strchr
0x383ad9557  mov     rsi, rax
0x383ad955a  test    rax, rax
0x383ad955d  jz      def_383AD95A1; jumptable 0000000383AD95A1 default case, cases 99-109,111-113,117
0x383ad9563  mov     ecx, eax
0x383ad9565  mov     [rax], r13b
0x383ad9568  sub     ecx, ebx
0x383ad956a  cmp     ecx, 0FFh
0x383ad9570  jg      def_383AD95A1; jumptable 0000000383AD95A1 default case, cases 99-109,111-113,117
0x383ad9576  movsx   ecx, byte ptr [rdi]
0x383ad9579  add     ecx, 0FFFFFF9Fh; switch 22 cases
0x383ad957c  cmp     ecx, 15h
0x383ad957f  ja      def_383AD95A1; jumptable 0000000383AD95A1 default case, cases 99-109,111-113,117
0x383ad9585  lea     rdx, cs:383800000h
0x383ad958c  movsxd  rax, ecx
0x383ad958f  movzx   eax, ds:(byte_383AD9824 - 383800000h)[rdx+rax]
0x383ad9597  mov     ecx, ds:(jpt_383AD95A1 - 383800000h)[rdx+rax*4]
0x383ad959e  add     rcx, rdx
0x383ad95a1  jmp     rcx; switch jump
0x383ad95a3  mov     edx, 1; jumptable 0000000383AD95A1 case 110
0x383ad95a8  mov     rcx, r14
0x383ad95ab  call    ?Find@ProtList@@QEAAPEAVProtElem@@W4ProviderNum@@@Z; ProtList::Find(ProviderNum)
0x383ad95b0  mov     rdi, rax
0x383ad95b3  test    rax, rax
0x383ad95b6  jz      loc_383AD973A; jumptable 0000000383AD95A1 cases 97,98,114,115,118
0x383ad95bc  mov     dword ptr [r15], 1
0x383ad95c3  add     r15, 4
0x383ad95c7  inc     ebp
0x383ad95c9  cmp     byte ptr [rbx], 5Ch ; '\'
0x383ad95cc  jnz     def_383AD95A1; jumptable 0000000383AD95A1 default case, cases 99-109,111-113,117
0x383ad95d2  cmp     byte ptr [rbx+1], 5Ch ; '\'
0x383ad95d6  jnz     def_383AD95A1; jumptable 0000000383AD95A1 default case, cases 99-109,111-113,117
0x383ad95dc  movzx   ecx, byte ptr [rbx+2]
0x383ad95e0  add     rbx, 2
0x383ad95e4  test    cl, cl
0x383ad95e6  jz      def_383AD95A1; jumptable 0000000383AD95A1 default case, cases 99-109,111-113,117
0x383ad95ec  nop     dword ptr [rax+00h]
0x383ad95f0  cmp     cl, 5Ch ; '\'
0x383ad95f3  jz      short loc_383AD9605
0x383ad95f5  movzx   ecx, byte ptr [rbx+1]
0x383ad95f9  inc     rbx
0x383ad95fc  test    cl, cl
0x383ad95fe  jnz     short loc_383AD95F0
0x383ad9600  jmp     def_383AD95A1; jumptable 0000000383AD95A1 default case, cases 99-109,111-113,117
0x383ad9605  cmp     [rbx], r13b
0x383ad9608  jz      def_383AD95A1; jumptable 0000000383AD95A1 default case, cases 99-109,111-113,117
0x383ad960e  mov     rcx, r12; lpString2
0x383ad9611  call    ?IsLocalHost@@YA_NPEBD@Z; IsLocalHost(char const *)
0x383ad9616  test    al, al
0x383ad9618  jz      short loc_383AD968F
0x383ad961a  lea     r8, VarName; "_CLUSTER_NETWORK_NAME_"
0x383ad9621  lea     rcx, [rsp+0B8h+Block]; Buffer
0x383ad9626  xor     edx, edx; BufferCount
0x383ad9628  call    cs:__imp__dupenv_s
0x383ad962e  test    eax, eax
0x383ad9630  jnz     def_383AD95A1; jumptable 0000000383AD95A1 default case, cases 99-109,111-113,117
0x383ad9636  mov     r8, [rsp+0B8h+Block]; lpString1
0x383ad963b  test    r8, r8
0x383ad963e  jz      short loc_383AD9666
0x383ad9640  or      r9d, 0FFFFFFFFh; cchCount1
0x383ad9644  mov     edx, 20001h; dwCmpFlags
0x383ad9649  mov     ecx, 800h; Locale
0x383ad964e  mov     [rsp+0B8h+cchCount2], 0FFFFFFFFh; cchCount2
0x383ad9656  mov     [rsp+0B8h+lpString2], r12; lpString2
0x383ad965b  call    cs:__imp_CompareStringA
0x383ad9661  cmp     eax, 2
0x383ad9664  jz      short loc_383AD968F
0x383ad9666  lea     rcx, [rdi+208h]; char *
0x383ad966d  lea     r8, aS_5; "\\\\.%s"
0x383ad9674  mov     r9, rbx
0x383ad9677  mov     edx, 105h; unsigned __int64
0x383ad967c  mov     [rdi+307h], r13b
0x383ad9683  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x383ad9688  test    eax, eax
0x383ad968a  jmp     loc_383AD9734
0x383ad968f  lea     rcx, [rdi+208h]; char *
0x383ad9696  lea     r8, aSS_11; "\\\\%s%s"
0x383ad969d  mov     r9, r12
0x383ad96a0  mov     edx, 105h; unsigned __int64
0x383ad96a5  mov     [rdi+307h], r13b
0x383ad96ac  mov     [rsp+0B8h+lpString2], rbx
0x383ad96b1  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x383ad96b6  test    eax, eax
0x383ad96b8  jmp     short loc_383AD9734
0x383ad96ba  mov     edx, 7; jumptable 0000000383AD95A1 case 116
0x383ad96bf  mov     rcx, r14
0x383ad96c2  call    ?Find@ProtList@@QEAAPEAVProtElem@@W4ProviderNum@@@Z; ProtList::Find(ProviderNum)
0x383ad96c7  mov     rdi, rax
0x383ad96ca  test    rax, rax
0x383ad96cd  jz      short loc_383AD973A; jumptable 0000000383AD95A1 cases 97,98,114,115,118
0x383ad96cf  mov     rcx, rbx; char *
0x383ad96d2  mov     dword ptr [r15], 7
0x383ad96d9  inc     ebp
0x383ad96db  add     r15, 4
0x383ad96df  call    ?Strtoi@@YAHPEBD@Z; Strtoi(char const *)
0x383ad96e4  test    eax, eax
0x383ad96e6  jz      def_383AD95A1; jumptable 0000000383AD95A1 default case, cases 99-109,111-113,117
0x383ad96ec  lea     rcx, [rdi+208h]
0x383ad96f3  mov     edx, 100h
0x383ad96f8  mov     r8d, r13d
0x383ad96fb  sub     rbx, rcx
0x383ad96fe  xchg    ax, ax
0x383ad9700  lea     rax, [rdx+7FFFFEFEh]
0x383ad9707  test    rax, rax
0x383ad970a  jz      short loc_383AD9720
0x383ad970c  movzx   eax, byte ptr [rbx+rcx]
0x383ad9710  test    al, al
0x383ad9712  jz      short loc_383AD9720
0x383ad9714  mov     [rcx], al
0x383ad9716  inc     rcx
0x383ad9719  dec     rdx
0x383ad971c  jnz     short loc_383AD9700
0x383ad971e  jmp     short loc_383AD9725
0x383ad9720  test    rdx, rdx
0x383ad9723  jnz     short loc_383AD972E
0x383ad9725  dec     rcx
0x383ad9728  mov     r8d, 8007007Ah
0x383ad972e  mov     [rcx], r13b
0x383ad9731  test    r8d, r8d
0x383ad9734  js      def_383AD95A1; jumptable 0000000383AD95A1 default case, cases 99-109,111-113,117
0x383ad973a  cmp     byte ptr [rsi+1], 3Bh ; ';'; jumptable 0000000383AD95A1 cases 97,98,114,115,118
0x383ad973e  lea     rdi, [rsi+1]
0x383ad9742  jnz     loc_383AD9520
0x383ad9748  mov     rdi, [r14]
0x383ad974b  movsxd  rbx, ebp
0x383ad974e  test    rdi, rdi
0x383ad9751  jz      short loc_383AD97AF
0x383ad9753  mov     rax, r13
0x383ad9756  test    rbx, rbx
0x383ad9759  jle     short loc_383AD976E
0x383ad975b  mov     ecx, [rdi]
0x383ad975d  nop     dword ptr [rax]
0x383ad9760  cmp     [rsp+rax*4+0B8h+var_80], ecx
0x383ad9764  jz      short loc_383AD976E
0x383ad9766  inc     rax
0x383ad9769  cmp     rax, rbx
0x383ad976c  jl      short loc_383AD9760
0x383ad976e  cmp     rax, rbx
0x383ad9771  jnz     short loc_383AD9798
0x383ad9773  mov     edx, [rdi]
0x383ad9775  mov     rdi, [rdi+408h]
0x383ad977c  cmp     edx, 4
0x383ad977f  jz      short loc_383AD97AA
0x383ad9781  mov     rcx, r14
0x383ad9784  call    ?RemoveProt@ProtList@@QEAAPEAVProtElem@@W4ProviderNum@@@Z; ProtList::RemoveProt(ProviderNum)
0x383ad9789  test    rax, rax
0x383ad978c  jz      short loc_383AD97AA
0x383ad978e  mov     rcx, rax; this
0x383ad9791  call    ??_GProtElem@@QEAAPEAXI@Z; ProtElem::`scalar deleting destructor'(uint)
0x383ad9796  jmp     short loc_383AD97AA
0x383ad9798  mov     ecx, dword ptr [rsp+rbx*4+0B8h+Block+4]
0x383ad979c  mov     rdi, [rdi+408h]
0x383ad97a3  dec     rbx
0x383ad97a6  mov     [rsp+rax*4+0B8h+var_80], ecx
0x383ad97aa  test    rdi, rdi
0x383ad97ad  jnz     short loc_383AD9753
0x383ad97af  mov     rcx, [rsp+0B8h+Block]; Block
0x383ad97b4  test    rcx, rcx
0x383ad97b7  jz      short loc_383AD97BF
0x383ad97b9  call    cs:__imp_free
0x383ad97bf  mov     eax, cs:_bidGblFlags
0x383ad97c5  and     eax, 20002h
0x383ad97ca  cmp     eax, 20002h
0x383ad97cf  jnz     short loc_383AD980D
0x383ad97d1  mov     rax, cs:off_383B48418; "<SSRP::ParseSsrpString|RET|SNI> success"...
0x383ad97d8  test    rax, rax
0x383ad97db  jz      short loc_383AD980D
0x383ad97dd  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x383ad97e5  jz      short loc_383AD980D
0x383ad97e7  mov     r9, cs:off_383B48418; "<SSRP::ParseSsrpString|RET|SNI> success"...
0x383ad97ee  mov     rdx, cs:off_383B45DB0; "d:\\b\\s1\\sources\\sql\\common\\dk\\sn"...
0x383ad97f5  mov     rcx, cs:_bidID
0x383ad97fc  mov     r8d, 0CD000h
0x383ad9802  mov     [rsp+0B8h+lpString2], r13
0x383ad9807  call    cs:off_383B15038
0x383ad980d  xor     eax, eax
0x383ad980f  jmp     loc_383AD94B3
```
