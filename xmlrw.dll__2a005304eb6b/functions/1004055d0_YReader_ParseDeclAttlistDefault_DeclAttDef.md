# YReader::ParseDeclAttlistDefault(DeclAttDef *)

- ea: `0x1004055d0`
- end: `0x1004058c0`
- name: `?ParseDeclAttlistDefault@YReader@@AEAAXPEAVDeclAttDef@@@Z`
- size: `752`
- prototype: `void __fastcall(YReader *__hidden this, struct DeclAttDef *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x100405110`

## callees

- `0x100401780`
- `0x1004018f0`
- `0x1004055d0`
- `0x10040a020`
- `0x10040a270`
- `0x10040b880`
- `0x10040bfc0`
- `0x10040c680`
- `0x100417b70`
- `0x100417c20`

## pseudocode

```c
void __fastcall YReader::ParseDeclAttlistDefault(YReader *this, struct DeclAttDef *a2)
{
  int v4; // eax
  int v5; // eax
  int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  unsigned int v10; // r8d
  __int64 v11; // rdx
  unsigned int v12; // r8d
  __int64 v13; // rdx
  __int64 v14; // rbx
  const wchar_t *v15; // rax
  unsigned int *v16; // r9
  int v17; // edx
  wchar_t *v18; // r8
  int v19; // eax
  unsigned int v20; // r8d
  __int64 v21; // rdx
  YReader *v22; // rcx
  int v23; // r8d

  v4 = YReader::GetTokenDeclInner(this) - 38;
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      v6 = v5 - 1;
      if ( v6 )
      {
        if ( v6 != 14 )
        {
LABEL_34:
          MXRRaiseException(-1072894419);
          __debugbreak();
        }
        *((_DWORD *)a2 + 32) = 1;
      }
      else
      {
        *((_DWORD *)a2 + 32) = 1;
        if ( (unsigned int)YReader::GetTokenDeclInner(this) != 54 )
        {
          MXRRaiseException(-1072894428);
          __debugbreak();
        }
      }
      *((_DWORD *)this + 1942) = 0;
      *((_DWORD *)this + 77) = 0x7FFFFFFF;
      v7 = YReader::GetTokenDeclLiteral(this) - 7;
      _mm_lfence();
      while ( 2 )
      {
        switch ( v7 )
        {
          case 0u:
            v8 = *((_DWORD *)this + 1942);
            if ( *((_DWORD *)this + 1943) == v8 )
            {
              _stack<AttValueToken,16>::grow((__int64)this + 7744, 0);
              v8 = *((_DWORD *)this + 1942);
            }
            v9 = *((_QWORD *)this + 970) + 24LL * v8;
            *((_DWORD *)this + 1942) = v8 + 1;
            *(_DWORD *)v9 = 7;
            YReader::GetTokenData(this, (struct StringPtr *)(v9 + 8));
            goto LABEL_26;
          case 1u:
          case 2u:
            v10 = *((_DWORD *)this + 1942);
            if ( *((_DWORD *)this + 1943) == v10 )
            {
              _stack<AttValueToken,16>::grow((__int64)this + 7744, 0);
              v10 = *((_DWORD *)this + 1942);
            }
            v11 = *((_QWORD *)this + 970) + 24LL * v10;
            *((_DWORD *)this + 1942) = v10 + 1;
            *(_DWORD *)v11 = *((_DWORD *)this + 28);
            *((_WORD *)this + 4132) = 32;
            *(_QWORD *)(v11 + 8) = (char *)this + 8264;
            *(_DWORD *)(v11 + 16) = 1;
            goto LABEL_26;
          case 3u:
            v12 = *((_DWORD *)this + 1942);
            if ( *((_DWORD *)this + 1943) == v12 )
            {
              _stack<AttValueToken,16>::grow((__int64)this + 7744, 0);
              v12 = *((_DWORD *)this + 1942);
            }
            v13 = *((_QWORD *)this + 970) + 24LL * v12;
            *((_DWORD *)this + 1942) = v12 + 1;
            v14 = v13 + 8;
            *(_DWORD *)v13 = 10;
            YReader::GetTokenData(this, (struct StringPtr *)(v13 + 8));
            v15 = *(const wchar_t **)v14;
            v16 = (unsigned int *)(v14 + 8);
            v17 = *(_DWORD *)(v14 + 8);
            v18 = *(wchar_t **)v14;
            if ( **(_WORD **)v14 == 120 )
              v19 = HexCharEntity2Utf16(v15 + 1, v17 - 1, v18, v16);
            else
              v19 = CharEntity2Utf16(v15, v17, v18, v16);
            if ( v19 < 0 )
            {
              _mm_lfence();
              MXRRaiseException(v19);
              __debugbreak();
            }
            goto LABEL_26;
          case 4u:
            v20 = *((_DWORD *)this + 1942);
            if ( *((_DWORD *)this + 1943) == v20 )
            {
              _stack<AttValueToken,16>::grow((__int64)this + 7744, 0);
              v20 = *((_DWORD *)this + 1942);
            }
            v21 = *((_QWORD *)this + 970) + 24LL * v20;
            *((_DWORD *)this + 1942) = v20 + 1;
            *(_DWORD *)v21 = 11;
            YReader::GetTokenData(this, (struct StringPtr *)(v21 + 8));
LABEL_26:
            v7 = YReader::GetTokenDeclLiteral(this) - 7;
            if ( v7 <= 0x2F )
              continue;
            goto LABEL_34;
          case 0x2Fu:
            _mm_lfence();
            YReader::NormalizeAttributeValue(this, (struct DeclAttDef *)((char *)a2 + 112));
            v23 = *((_DWORD *)a2 + 43);
            if ( v23 )
              YReader::NormalizeTypedAttributeValue(v22, (struct DeclAttDef *)((char *)a2 + 112), v23);
            return;
          default:
            goto LABEL_34;
        }
      }
    }
  }
  *((_DWORD *)a2 + 32) = 0;
}

```

## disassembly

```asm
0x1004055d0  mov     [rsp+arg_18], rsi
0x1004055d5  push    rdi
0x1004055d6  sub     rsp, 20h
0x1004055da  mov     rsi, rdx
0x1004055dd  mov     rdi, rcx
0x1004055e0  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x1004055e5  sub     eax, 26h ; '&'
0x1004055e8  jz      loc_100405840
0x1004055ee  sub     eax, 1
0x1004055f1  jz      loc_100405840
0x1004055f7  mov     [rsp+28h+arg_0], rbx
0x1004055fc  mov     [rsp+28h+arg_8], rbp
0x100405601  mov     [rsp+28h+arg_10], r14
0x100405606  sub     eax, 1
0x100405609  jz      short loc_10040566C
0x10040560b  cmp     eax, 0Eh
0x10040560e  jnz     def_10040566A; jumptable 000000010040566A default case, cases 12-53
0x100405614  mov     dword ptr [rsi+80h], 1
0x10040561e  mov     rcx, rdi; this
0x100405621  mov     dword ptr [rdi+1E58h], 0
0x10040562b  mov     dword ptr [rdi+134h], 7FFFFFFFh
0x100405635  call    ?GetTokenDeclLiteral@YReader@@AEAAHXZ; YReader::GetTokenDeclLiteral(void)
0x10040563a  sub     eax, 7; switch 48 cases
0x10040563d  cmp     eax, 2Fh
0x100405640  ja      def_10040566A; jumptable 000000010040566A default case, cases 12-53
0x100405646  lfence
0x100405649  lea     rbp, __ImageBase
0x100405650  mov     r14d, 20h ; ' '
0x100405656  cdqe
0x100405658  movzx   eax, ds:(byte_100405890 - 100400000h)[rax+rbp]
0x100405660  mov     ecx, ss:(jpt_10040566A - 100400000h)[rbp+rax*4]
0x100405667  add     rcx, rbp
0x10040566a  jmp     rcx; switch jump
0x10040566c  mov     rcx, rdi; this
0x10040566f  mov     dword ptr [rsi+80h], 1
0x100405679  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x10040567e  cmp     eax, 36h ; '6'
0x100405681  jnz     loc_100405855
0x100405687  jmp     short loc_10040561E
0x100405689  lea     rbx, [rdi+1E40h]; jumptable 000000010040566A case 7
0x100405690  mov     r8d, [rbx+18h]
0x100405694  cmp     [rbx+1Ch], r8d
0x100405698  jnz     short loc_1004056A8
0x10040569a  xor     edx, edx
0x10040569c  mov     rcx, rbx
0x10040569f  call    ?grow@?$_stack@UAttValueToken@@$0BA@@@AEAAXI@Z; _stack<AttValueToken,16>::grow(uint)
0x1004056a4  mov     r8d, [rbx+18h]
0x1004056a8  mov     eax, r8d
0x1004056ab  lea     rcx, [rax+rax*2]
0x1004056af  mov     rax, [rbx+10h]
0x1004056b3  lea     rdx, [rax+rcx*8]
0x1004056b7  mov     rcx, rdi; this
0x1004056ba  lea     eax, [r8+1]
0x1004056be  mov     [rbx+18h], eax
0x1004056c1  mov     dword ptr [rdx], 7
0x1004056c7  add     rdx, 8; struct StringPtr *
0x1004056cb  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x1004056d0  jmp     loc_1004057ED
0x1004056d5  lea     rbx, [rdi+1E40h]; jumptable 000000010040566A cases 8,9
0x1004056dc  mov     r8d, [rbx+18h]
0x1004056e0  cmp     [rbx+1Ch], r8d
0x1004056e4  jnz     short loc_1004056F4
0x1004056e6  xor     edx, edx
0x1004056e8  mov     rcx, rbx
0x1004056eb  call    ?grow@?$_stack@UAttValueToken@@$0BA@@@AEAAXI@Z; _stack<AttValueToken,16>::grow(uint)
0x1004056f0  mov     r8d, [rbx+18h]
0x1004056f4  mov     eax, r8d
0x1004056f7  lea     rcx, [rax+rax*2]
0x1004056fb  mov     rax, [rbx+10h]
0x1004056ff  lea     rdx, [rax+rcx*8]
0x100405703  lea     eax, [r8+1]
0x100405707  mov     [rbx+18h], eax
0x10040570a  mov     eax, [rdi+70h]
0x10040570d  mov     [rdx], eax
0x10040570f  lea     rax, [rdi+2048h]
0x100405716  mov     [rax], r14w
0x10040571a  mov     [rdx+8], rax
0x10040571e  mov     dword ptr [rdx+10h], 1
0x100405725  jmp     loc_1004057ED
0x10040572a  lea     rbx, [rdi+1E40h]; jumptable 000000010040566A case 10
0x100405731  mov     r8d, [rbx+18h]
0x100405735  cmp     [rbx+1Ch], r8d
0x100405739  jnz     short loc_100405749
0x10040573b  xor     edx, edx
0x10040573d  mov     rcx, rbx
0x100405740  call    ?grow@?$_stack@UAttValueToken@@$0BA@@@AEAAXI@Z; _stack<AttValueToken,16>::grow(uint)
0x100405745  mov     r8d, [rbx+18h]
0x100405749  mov     eax, r8d
0x10040574c  lea     rcx, [rax+rax*2]
0x100405750  mov     rax, [rbx+10h]
0x100405754  lea     rdx, [rax+rcx*8]
0x100405758  mov     rcx, rdi; this
0x10040575b  lea     eax, [r8+1]
0x10040575f  mov     [rbx+18h], eax
0x100405762  lea     rbx, [rdx+8]
0x100405766  mov     dword ptr [rdx], 0Ah
0x10040576c  mov     rdx, rbx; struct StringPtr *
0x10040576f  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x100405774  mov     rax, [rbx]
0x100405777  lea     r9, [rbx+8]; unsigned int *
0x10040577b  mov     edx, [r9]; int
0x10040577e  mov     r8, rax; wchar_t *
0x100405781  cmp     word ptr [rax], 78h ; 'x'
0x100405785  jnz     short loc_100405794
0x100405787  dec     edx; int
0x100405789  lea     rcx, [rax+2]; wchar_t *
0x10040578d  call    ?HexCharEntity2Utf16@@YAJPEB_WHPEA_WPEAI@Z; HexCharEntity2Utf16(wchar_t const *,int,wchar_t *,uint *)
0x100405792  jmp     short loc_10040579C
0x100405794  mov     rcx, rax; wchar_t *
0x100405797  call    ?CharEntity2Utf16@@YAJPEB_WHPEA_WPEAI@Z; CharEntity2Utf16(wchar_t const *,int,wchar_t *,uint *)
0x10040579c  test    eax, eax
0x10040579e  js      loc_100405860
0x1004057a4  jmp     short loc_1004057ED
0x1004057a6  lea     rbx, [rdi+1E40h]; jumptable 000000010040566A case 11
0x1004057ad  mov     r8d, [rbx+18h]
0x1004057b1  cmp     [rbx+1Ch], r8d
0x1004057b5  jnz     short loc_1004057C5
0x1004057b7  xor     edx, edx
0x1004057b9  mov     rcx, rbx
0x1004057bc  call    ?grow@?$_stack@UAttValueToken@@$0BA@@@AEAAXI@Z; _stack<AttValueToken,16>::grow(uint)
0x1004057c1  mov     r8d, [rbx+18h]
0x1004057c5  mov     eax, r8d
0x1004057c8  lea     rcx, [rax+rax*2]
0x1004057cc  mov     rax, [rbx+10h]
0x1004057d0  lea     rdx, [rax+rcx*8]
0x1004057d4  mov     rcx, rdi; this
0x1004057d7  lea     eax, [r8+1]
0x1004057db  mov     [rbx+18h], eax
0x1004057de  mov     dword ptr [rdx], 0Bh
0x1004057e4  add     rdx, 8; struct StringPtr *
0x1004057e8  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x1004057ed  mov     rcx, rdi; this
0x1004057f0  call    ?GetTokenDeclLiteral@YReader@@AEAAHXZ; YReader::GetTokenDeclLiteral(void)
0x1004057f5  sub     eax, 7
0x1004057f8  cmp     eax, 2Fh ; '/'
0x1004057fb  ja      short def_10040566A; jumptable 000000010040566A default case, cases 12-53
0x1004057fd  jmp     loc_100405656
0x100405802  lfence; jumptable 000000010040566A case 54
0x100405805  lea     rdx, [rsi+70h]; struct StringPtr *
0x100405809  mov     rcx, rdi; this
0x10040580c  call    ?NormalizeAttributeValue@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::NormalizeAttributeValue(StringPtr *)
0x100405811  mov     r8d, [rsi+0ACh]; int
0x100405818  test    r8d, r8d
0x10040581b  jz      short loc_100405826
0x10040581d  lea     rdx, [rsi+70h]; struct StringPtr *
0x100405821  call    ?NormalizeTypedAttributeValue@YReader@@AEAAXPEAUStringPtr@@H@Z; YReader::NormalizeTypedAttributeValue(StringPtr *,int)
0x100405826  mov     rbp, [rsp+28h+arg_8]
0x10040582b  mov     rbx, [rsp+28h+arg_0]
0x100405830  mov     r14, [rsp+28h+arg_10]
0x100405835  mov     rsi, [rsp+28h+arg_18]
0x10040583a  add     rsp, 20h
0x10040583e  pop     rdi
0x10040583f  retn
0x100405840  mov     dword ptr [rsi+80h], 0
0x10040584a  mov     rsi, [rsp+28h+arg_18]
0x10040584f  add     rsp, 20h
0x100405853  pop     rdi
0x100405854  retn
0x100405855  mov     ecx, 0C00CEE24h; int
0x10040585a  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040585f  int     3; Trap to Debugger
0x100405860  lfence
0x100405863  mov     ecx, eax; int
0x100405865  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040586a  int     3; Trap to Debugger
0x10040586b  mov     ecx, 0C00CEE2Dh; jumptable 000000010040566A default case, cases 12-53
0x100405870  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100405875  int     3; Trap to Debugger
```
