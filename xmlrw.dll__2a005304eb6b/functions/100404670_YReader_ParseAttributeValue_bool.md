# YReader::ParseAttributeValue(bool)

- ea: `0x100404670`
- end: `0x1004048f0`
- name: `?ParseAttributeValue@YReader@@AEAAX_N@Z`
- size: `640`
- prototype: `void __fastcall(YReader *this, char)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1004038d0`
- `0x100403ba0`
- `0x100404070`
- `0x100404310`

## callees

- `0x100401780`
- `0x1004018f0`
- `0x100404670`
- `0x10040c680`
- `0x100417b70`
- `0x100417c20`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseAttributeValue(YReader *this, char a2)
{
  int v3; // ecx
  int v4; // eax
  unsigned int v5; // r8d
  __int64 v6; // rdx
  unsigned int v7; // r8d
  __int64 v8; // rdx
  __int64 v9; // rbx
  const wchar_t *v10; // rax
  unsigned int *v11; // r9
  int v12; // edx
  wchar_t *v13; // r8
  int v14; // eax
  unsigned int v15; // r8d
  __int64 v16; // rdx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  int v19; // eax
  void (__fastcall *v20)(Scanner *__hidden); // rax

  if ( a2 )
    v3 = *((_DWORD *)this + 458);
  else
    v3 = 0;
  *((_DWORD *)this + 1942) = 0;
  v4 = 0x7FFFFFFF;
  if ( v3 > 0 )
    v4 = v3;
  *((_DWORD *)this + 77) = v4;
  while ( 1 )
  {
    while ( 1 )
    {
      (*((void (__fastcall **)(char *))this + 27))((char *)this + 40);
      switch ( *((_DWORD *)this + 28) )
      {
        case 7:
          v17 = *((_DWORD *)this + 1942);
          if ( *((_DWORD *)this + 1943) == v17 )
          {
            _stack<AttValueToken,16>::grow((__int64)this + 7744, 0);
            v17 = *((_DWORD *)this + 1942);
          }
          v18 = *((_QWORD *)this + 970) + 24LL * v17;
          *((_DWORD *)this + 1942) = v17 + 1;
          *(_DWORD *)v18 = 7;
          YReader::GetTokenData(this, (struct StringPtr *)(v18 + 8));
          break;
        case 8:
        case 9:
          v15 = *((_DWORD *)this + 1942);
          if ( *((_DWORD *)this + 1943) == v15 )
          {
            _stack<AttValueToken,16>::grow((__int64)this + 7744, 0);
            v15 = *((_DWORD *)this + 1942);
          }
          v16 = *((_QWORD *)this + 970) + 24LL * v15;
          *((_DWORD *)this + 1942) = v15 + 1;
          *(_DWORD *)v16 = *((_DWORD *)this + 28);
          *((_WORD *)this + 4132) = 32;
          *(_QWORD *)(v16 + 8) = (char *)this + 8264;
          *(_DWORD *)(v16 + 16) = 1;
          break;
        case 0xA:
          v7 = *((_DWORD *)this + 1942);
          if ( *((_DWORD *)this + 1943) == v7 )
          {
            _stack<AttValueToken,16>::grow((__int64)this + 7744, 0);
            v7 = *((_DWORD *)this + 1942);
          }
          v8 = *((_QWORD *)this + 970) + 24LL * v7;
          *((_DWORD *)this + 1942) = v7 + 1;
          v9 = v8 + 8;
          *(_DWORD *)v8 = 10;
          YReader::GetTokenData(this, (struct StringPtr *)(v8 + 8));
          v10 = *(const wchar_t **)v9;
          v11 = (unsigned int *)(v9 + 8);
          v12 = *(_DWORD *)(v9 + 8);
          v13 = *(wchar_t **)v9;
          if ( **(_WORD **)v9 == 120 )
            v14 = HexCharEntity2Utf16(v10 + 1, v12 - 1, v13, v11);
          else
            v14 = CharEntity2Utf16(v10, v12, v13, v11);
          if ( v14 < 0 )
          {
            _mm_lfence();
            MXRRaiseException(v14);
            JUMPOUT(0x1004048EFLL);
          }
          break;
        case 0xB:
          v5 = *((_DWORD *)this + 1942);
          if ( *((_DWORD *)this + 1943) == v5 )
          {
            _stack<AttValueToken,16>::grow((__int64)this + 7744, 0);
            v5 = *((_DWORD *)this + 1942);
          }
          v6 = *((_QWORD *)this + 970) + 24LL * v5;
          *((_DWORD *)this + 1942) = v5 + 1;
          *(_DWORD *)v6 = 11;
          YReader::GetTokenData(this, (struct StringPtr *)(v6 + 8));
          break;
        default:
          return;
      }
      v19 = *((_DWORD *)this + 78);
      if ( !v19 )
        break;
      if ( v19 > 0 )
        return;
    }
    if ( *((int *)this + 77) <= 0 )
    {
      v20 = (void (__fastcall *)(Scanner *__hidden))*((_QWORD *)this + 27);
      if ( v20 == Scanner::ScanAttributeValue
        || v20 == Scanner::ScanCdSectData
        || v20 == Scanner::ScanCommentData
        || v20 == Scanner::ScanPiData )
      {
        break;
      }
    }
  }
  *((_DWORD *)this + 78) = 1;
}

```

## disassembly

```asm
0x100404670  mov     [rsp+arg_8], rbp
0x100404675  mov     [rsp+arg_10], rsi
0x10040467a  push    rdi
0x10040467b  push    r12
0x10040467d  push    r13
0x10040467f  push    r14
0x100404681  push    r15
0x100404683  sub     rsp, 20h
0x100404687  mov     rdi, rcx
0x10040468a  test    dl, dl
0x10040468c  jz      short loc_100404696
0x10040468e  mov     ecx, [rcx+728h]
0x100404694  jmp     short loc_100404698
0x100404696  xor     ecx, ecx
0x100404698  test    ecx, ecx
0x10040469a  mov     dword ptr [rdi+1E58h], 0
0x1004046a4  mov     eax, 7FFFFFFFh
0x1004046a9  mov     [rsp+48h+arg_0], rbx
0x1004046ae  cmovg   eax, ecx
0x1004046b1  lea     rbp, ?ScanAttributeValue@Scanner@@AEAAXXZ; Scanner::ScanAttributeValue(void)
0x1004046b8  mov     [rdi+134h], eax
0x1004046be  lea     r14, ?ScanCdSectData@Scanner@@AEAAXXZ; Scanner::ScanCdSectData(void)
0x1004046c5  mov     r13d, 20h ; ' '
0x1004046cb  lea     r15, ?ScanCommentData@Scanner@@AEAAXXZ; Scanner::ScanCommentData(void)
0x1004046d2  lea     r12, ?ScanPiData@Scanner@@AEAAXXZ; Scanner::ScanPiData(void)
0x1004046d9  nop     dword ptr [rax+00000000h]
0x1004046e0  mov     rax, [rdi+0D8h]
0x1004046e7  lea     rcx, [rdi+28h]
0x1004046eb  call    cs:__guard_dispatch_icall_fptr
0x1004046f1  mov     eax, [rdi+70h]
0x1004046f4  sub     eax, 7
0x1004046f7  jz      loc_10040483A
0x1004046fd  sub     eax, 1
0x100404700  jz      loc_1004047E8
0x100404706  sub     eax, 1
0x100404709  jz      loc_1004047E8
0x10040470f  sub     eax, 1
0x100404712  jz      short loc_100404769
0x100404714  cmp     eax, 1
0x100404717  jnz     loc_1004048C0
0x10040471d  lea     rbx, [rdi+1E40h]
0x100404724  mov     r8d, [rbx+18h]
0x100404728  cmp     [rbx+1Ch], r8d
0x10040472c  jnz     short loc_10040473C
0x10040472e  xor     edx, edx
0x100404730  mov     rcx, rbx
0x100404733  call    ?grow@?$_stack@UAttValueToken@@$0BA@@@AEAAXI@Z; _stack<AttValueToken,16>::grow(uint)
0x100404738  mov     r8d, [rbx+18h]
0x10040473c  mov     eax, r8d
0x10040473f  lea     rcx, [rax+rax*2]
0x100404743  mov     rax, [rbx+10h]
0x100404747  lea     rdx, [rax+rcx*8]
0x10040474b  mov     rcx, rdi; this
0x10040474e  lea     eax, [r8+1]
0x100404752  mov     [rbx+18h], eax
0x100404755  mov     dword ptr [rdx], 0Bh
0x10040475b  add     rdx, 8; struct StringPtr *
0x10040475f  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x100404764  jmp     loc_100404881
0x100404769  lea     rbx, [rdi+1E40h]
0x100404770  mov     r8d, [rbx+18h]
0x100404774  cmp     [rbx+1Ch], r8d
0x100404778  jnz     short loc_100404788
0x10040477a  xor     edx, edx
0x10040477c  mov     rcx, rbx
0x10040477f  call    ?grow@?$_stack@UAttValueToken@@$0BA@@@AEAAXI@Z; _stack<AttValueToken,16>::grow(uint)
0x100404784  mov     r8d, [rbx+18h]
0x100404788  mov     eax, r8d
0x10040478b  lea     rcx, [rax+rax*2]
0x10040478f  mov     rax, [rbx+10h]
0x100404793  lea     rdx, [rax+rcx*8]
0x100404797  mov     rcx, rdi; this
0x10040479a  lea     eax, [r8+1]
0x10040479e  mov     [rbx+18h], eax
0x1004047a1  lea     rbx, [rdx+8]
0x1004047a5  mov     dword ptr [rdx], 0Ah
0x1004047ab  mov     rdx, rbx; struct StringPtr *
0x1004047ae  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x1004047b3  mov     rax, [rbx]
0x1004047b6  lea     r9, [rbx+8]; unsigned int *
0x1004047ba  mov     edx, [r9]; int
0x1004047bd  mov     r8, rax; wchar_t *
0x1004047c0  cmp     word ptr [rax], 78h ; 'x'
0x1004047c4  jnz     short loc_1004047D3
0x1004047c6  dec     edx; int
0x1004047c8  lea     rcx, [rax+2]; wchar_t *
0x1004047cc  call    ?HexCharEntity2Utf16@@YAJPEB_WHPEA_WPEAI@Z; HexCharEntity2Utf16(wchar_t const *,int,wchar_t *,uint *)
0x1004047d1  jmp     short loc_1004047DB
0x1004047d3  mov     rcx, rax; wchar_t *
0x1004047d6  call    ?CharEntity2Utf16@@YAJPEB_WHPEA_WPEAI@Z; CharEntity2Utf16(wchar_t const *,int,wchar_t *,uint *)
0x1004047db  test    eax, eax
0x1004047dd  js      loc_1004048E5
0x1004047e3  jmp     loc_100404881
0x1004047e8  lea     rbx, [rdi+1E40h]
0x1004047ef  mov     r8d, [rbx+18h]
0x1004047f3  cmp     [rbx+1Ch], r8d
0x1004047f7  jnz     short loc_100404807
0x1004047f9  xor     edx, edx
0x1004047fb  mov     rcx, rbx
0x1004047fe  call    ?grow@?$_stack@UAttValueToken@@$0BA@@@AEAAXI@Z; _stack<AttValueToken,16>::grow(uint)
0x100404803  mov     r8d, [rbx+18h]
0x100404807  mov     eax, r8d
0x10040480a  lea     rcx, [rax+rax*2]
0x10040480e  mov     rax, [rbx+10h]
0x100404812  lea     rdx, [rax+rcx*8]
0x100404816  lea     eax, [r8+1]
0x10040481a  mov     [rbx+18h], eax
0x10040481d  mov     eax, [rdi+70h]
0x100404820  mov     [rdx], eax
0x100404822  lea     rax, [rdi+2048h]
0x100404829  mov     [rax], r13w
0x10040482d  mov     [rdx+8], rax
0x100404831  mov     dword ptr [rdx+10h], 1
0x100404838  jmp     short loc_100404881
0x10040483a  lea     rbx, [rdi+1E40h]
0x100404841  mov     r8d, [rbx+18h]
0x100404845  cmp     [rbx+1Ch], r8d
0x100404849  jnz     short loc_100404859
0x10040484b  xor     edx, edx
0x10040484d  mov     rcx, rbx
0x100404850  call    ?grow@?$_stack@UAttValueToken@@$0BA@@@AEAAXI@Z; _stack<AttValueToken,16>::grow(uint)
0x100404855  mov     r8d, [rbx+18h]
0x100404859  mov     eax, r8d
0x10040485c  lea     rcx, [rax+rax*2]
0x100404860  mov     rax, [rbx+10h]
0x100404864  lea     rdx, [rax+rcx*8]
0x100404868  mov     rcx, rdi; this
0x10040486b  lea     eax, [r8+1]
0x10040486f  mov     [rbx+18h], eax
0x100404872  mov     dword ptr [rdx], 7
0x100404878  add     rdx, 8; struct StringPtr *
0x10040487c  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x100404881  mov     eax, [rdi+138h]
0x100404887  test    eax, eax
0x100404889  jnz     short loc_1004048DD
0x10040488b  cmp     [rdi+134h], eax
0x100404891  jg      loc_1004046E0
0x100404897  mov     rax, [rdi+0D8h]
0x10040489e  cmp     rax, rbp
0x1004048a1  jz      short loc_1004048B6
0x1004048a3  cmp     rax, r14
0x1004048a6  jz      short loc_1004048B6
0x1004048a8  cmp     rax, r15
0x1004048ab  jz      short loc_1004048B6
0x1004048ad  cmp     rax, r12
0x1004048b0  jnz     loc_1004046E0
0x1004048b6  mov     dword ptr [rdi+138h], 1
0x1004048c0  mov     rbx, [rsp+48h+arg_0]
0x1004048c5  mov     rbp, [rsp+48h+arg_8]
0x1004048ca  mov     rsi, [rsp+48h+arg_10]
0x1004048cf  add     rsp, 20h
0x1004048d3  pop     r15
0x1004048d5  pop     r14
0x1004048d7  pop     r13
0x1004048d9  pop     r12
0x1004048db  pop     rdi
0x1004048dc  retn
0x1004048dd  jle     loc_1004046E0
0x1004048e3  jmp     short loc_1004048C0
0x1004048e5  lfence
0x1004048e8  mov     ecx, eax; int
0x1004048ea  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
