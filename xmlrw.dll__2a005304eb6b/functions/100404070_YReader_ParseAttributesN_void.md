# YReader::ParseAttributesN(void)

- ea: `0x100404070`
- end: `0x1004042ff`
- name: `?ParseAttributesN@YReader@@AEAAXXZ`
- size: `655`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, registry_config, broker_com_uri`

## callees

- `0x100401780`
- `0x1004019c0`
- `0x100404070`
- `0x100404670`
- `0x10040b880`
- `0x10040c7b0`
- `0x100415950`
- `0x1004394f0`
- `0x100439df0`

## pseudocode

```c
void __fastcall YReader::ParseAttributesN(YReader *this)
{
  unsigned int v2; // ecx
  __int64 v3; // rbx
  __int64 v4; // r14
  unsigned int v5; // eax
  struct StringPtr *v6; // rdx
  __int128 v7; // xmm1
  unsigned int v8; // ecx
  __int64 v9; // rcx
  __int64 v10; // rax
  unsigned int v11; // eax
  int v12; // eax
  void (__fastcall *v13)(YReader *__hidden); // rax
  __int128 v14; // [rsp+20h] [rbp-28h] BYREF

  *((_DWORD *)this + 710) = 0;
  *((_DWORD *)this + 1326) = 0;
  (*((void (**)(void))this + 27))();
  while ( *((_DWORD *)this + 28) != 5 )
  {
    switch ( *((_DWORD *)this + 28) )
    {
      case 6:
        *((_DWORD *)this + 444) = 1;
        v13 = YReader::ParseEETagEnd;
        goto LABEL_22;
      case 0xC:
        v2 = *((_DWORD *)this + 710);
        if ( *((_DWORD *)this + 711) == v2 )
        {
          _stack<Attribute,16>::grow((char *)this + 2816);
          v2 = *((_DWORD *)this + 710);
        }
        v3 = *((_QWORD *)this + 354) + 152LL * v2;
        *((_DWORD *)this + 710) = v2 + 1;
        YReader::GetTokenQName(this, (struct StringPtr *)v3, (struct StringPtr *)(v3 + 16));
        *(_DWORD *)(v3 + 96) = 0;
        *(_OWORD *)(v3 + 64) = CodeStringPtr::CDATA;
        YReader::ParseAttributeValue(this, 0);
        YReader::NormalizeAttributeValue(this, (struct StringPtr *)(v3 + 80));
        v4 = *(unsigned int *)(v3 + 24);
        *(_QWORD *)(v3 + 104) = 0;
        if ( (_DWORD)v4 )
        {
          v11 = *(_DWORD *)(v3 + 24);
          if ( v11 != dword_100450B48 || memcmp(*(const void **)(v3 + 16), CodeStringPtr::xmlns, 2LL * v11) )
            goto LABEL_19;
          v6 = (struct StringPtr *)&v14;
          v12 = *(_DWORD *)(v3 + 8) - v4;
          *(_QWORD *)&v14 = *(_QWORD *)v3 + 2 * (v4 + 1);
          DWORD2(v14) = v12 - 1;
LABEL_13:
          NamespaceSupport::PushPrefix((YReader *)((char *)this + 512), v6, (struct StringPtr *)(v3 + 80));
          *(_OWORD *)(v3 + 32) = *(_OWORD *)&CodeStringPtr::xmlnsUri;
          v7 = CodeStringPtr::empty;
          *(_DWORD *)(v3 + 100) = 1;
          *(_OWORD *)(v3 + 48) = v7;
          v8 = *((_DWORD *)this + 1326);
          if ( *((_DWORD *)this + 1327) == v8 )
          {
            _stack<Attribute,16>::grow((char *)this + 5280);
            v8 = *((_DWORD *)this + 1326);
          }
          *((_DWORD *)this + 1326) = v8 + 1;
          v9 = 152LL * v8;
          v10 = *((_QWORD *)this + 662);
          *(_OWORD *)(v9 + v10) = *(_OWORD *)v3;
          *(_OWORD *)(v9 + v10 + 16) = *(_OWORD *)(v3 + 16);
          *(_OWORD *)(v9 + v10 + 32) = *(_OWORD *)(v3 + 32);
          *(_OWORD *)(v9 + v10 + 48) = *(_OWORD *)(v3 + 48);
          *(_OWORD *)(v9 + v10 + 64) = *(_OWORD *)(v3 + 64);
          *(_OWORD *)(v9 + v10 + 80) = *(_OWORD *)(v3 + 80);
          *(_OWORD *)(v9 + v10 + 96) = *(_OWORD *)(v3 + 96);
          *(_OWORD *)(v9 + v10 + 112) = *(_OWORD *)(v3 + 112);
          *(_OWORD *)(v9 + v10 + 128) = *(_OWORD *)(v3 + 128);
          *(_QWORD *)(v9 + v10 + 144) = *(_QWORD *)(v3 + 144);
          --*((_DWORD *)this + 710);
        }
        else
        {
          v5 = *(_DWORD *)(v3 + 8);
          if ( v5 == dword_100450B48 && !memcmp(*(const void **)v3, CodeStringPtr::xmlns, 2LL * v5) )
          {
            v6 = (struct StringPtr *)&CodeStringPtr::empty;
            goto LABEL_13;
          }
LABEL_19:
          *(_DWORD *)(v3 + 100) = 0;
        }
        break;
      case 0x3B:
        MXRRaiseException(-1072894463);
        JUMPOUT(0x1004042FELL);
    }
  }
  *((_DWORD *)this + 444) = 2;
  v13 = YReader::ParseTagEnd;
LABEL_22:
  *(_QWORD *)&v14 = v13;
  DWORD2(v14) = 0;
  *((_OWORD *)this + 94) = v14;
}

```

## disassembly

```asm
0x100404070  push    rdi
0x100404072  push    r15
0x100404074  sub     rsp, 38h
0x100404078  xor     r15d, r15d
0x10040407b  mov     rdi, rcx
0x10040407e  mov     [rcx+0B18h], r15d
0x100404085  mov     [rcx+14B8h], r15d
0x10040408c  add     rcx, 28h ; '('
0x100404090  mov     rax, [rcx+0B0h]
0x100404097  call    cs:__guard_dispatch_icall_fptr
0x10040409d  mov     [rsp+48h+arg_0], rbx
0x1004040a2  mov     [rsp+48h+arg_8], rbp
0x1004040a7  mov     [rsp+48h+arg_10], rsi
0x1004040ac  mov     [rsp+48h+var_18], r14
0x1004040b1  mov     ecx, [rdi+70h]
0x1004040b4  sub     ecx, 5
0x1004040b7  jz      loc_1004042B1
0x1004040bd  sub     ecx, 1
0x1004040c0  jz      loc_10040429E
0x1004040c6  sub     ecx, 6
0x1004040c9  jz      short loc_1004040D6
0x1004040cb  cmp     ecx, 2Fh ; '/'
0x1004040ce  jz      loc_1004042F4
0x1004040d4  jmp     short loc_1004040B1
0x1004040d6  lea     rsi, [rdi+0B00h]
0x1004040dd  mov     ecx, [rsi+18h]
0x1004040e0  cmp     [rsi+1Ch], ecx
0x1004040e3  jnz     short loc_1004040F2
0x1004040e5  xor     edx, edx
0x1004040e7  mov     rcx, rsi
0x1004040ea  call    ?grow@?$_stack@UAttribute@@$0BA@@@AEAAXI@Z; _stack<Attribute,16>::grow(uint)
0x1004040ef  mov     ecx, [rsi+18h]
0x1004040f2  mov     eax, ecx
0x1004040f4  imul    rbx, rax, 98h
0x1004040fb  lea     eax, [rcx+1]
0x1004040fe  mov     rcx, rdi; this
0x100404101  add     rbx, [rsi+10h]
0x100404105  mov     rdx, rbx; struct StringPtr *
0x100404108  mov     [rsi+18h], eax
0x10040410b  lea     r8, [rbx+10h]; struct StringPtr *
0x10040410f  call    ?GetTokenQName@YReader@@AEAAXPEAUStringPtr@@0@Z; YReader::GetTokenQName(StringPtr *,StringPtr *)
0x100404114  movups  xmm0, xmmword ptr cs:?CDATA@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::CDATA
0x10040411b  xor     edx, edx; bool
0x10040411d  mov     [rbx+60h], r15d
0x100404121  mov     rcx, rdi; this
0x100404124  movups  xmmword ptr [rbx+40h], xmm0
0x100404128  call    ?ParseAttributeValue@YReader@@AEAAX_N@Z; YReader::ParseAttributeValue(bool)
0x10040412d  lea     rdx, [rbx+50h]; struct StringPtr *
0x100404131  mov     rcx, rdi; this
0x100404134  call    ?NormalizeAttributeValue@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::NormalizeAttributeValue(StringPtr *)
0x100404139  mov     r14d, [rbx+18h]
0x10040413d  mov     [rbx+68h], r15
0x100404141  test    r14d, r14d
0x100404144  jnz     loc_10040424A
0x10040414a  mov     eax, [rbx+8]
0x10040414d  cmp     eax, cs:dword_100450B48
0x100404153  jnz     loc_100404295
0x100404159  mov     rdx, cs:?xmlns@CodeStringPtr@@2UStringPtr@@A; Buf2
0x100404160  mov     r8d, eax
0x100404163  mov     rcx, [rbx]; Buf1
0x100404166  add     r8, r8; Size
0x100404169  call    memcmp
0x10040416e  test    eax, eax
0x100404170  jnz     loc_100404295
0x100404176  lea     rdx, ?empty@CodeStringPtr@@2UStringPtr@@A; struct StringPtr *
0x10040417d  lea     r8, [rbx+50h]; struct StringPtr *
0x100404181  lea     rcx, [rdi+200h]; this
0x100404188  call    ?PushPrefix@NamespaceSupport@@QEAAXPEAUStringPtr@@0@Z; NamespaceSupport::PushPrefix(StringPtr *,StringPtr *)
0x10040418d  movups  xmm0, xmmword ptr cs:?xmlnsUri@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::xmlnsUri
0x100404194  lea     rsi, [rdi+14A0h]
0x10040419b  movups  xmmword ptr [rbx+20h], xmm0
0x10040419f  movups  xmm1, xmmword ptr cs:?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x1004041a6  mov     dword ptr [rbx+64h], 1
0x1004041ad  movups  xmmword ptr [rbx+30h], xmm1
0x1004041b1  mov     ecx, [rsi+18h]
0x1004041b4  cmp     [rsi+1Ch], ecx
0x1004041b7  jnz     short loc_1004041C6
0x1004041b9  xor     edx, edx
0x1004041bb  mov     rcx, rsi
0x1004041be  call    ?grow@?$_stack@UAttribute@@$0BA@@@AEAAXI@Z; _stack<Attribute,16>::grow(uint)
0x1004041c3  mov     ecx, [rsi+18h]
0x1004041c6  lea     eax, [rcx+1]
0x1004041c9  mov     [rsi+18h], eax
0x1004041cc  movups  xmm0, xmmword ptr [rbx]
0x1004041cf  mov     eax, ecx
0x1004041d1  imul    rcx, rax, 98h
0x1004041d8  mov     rax, [rsi+10h]
0x1004041dc  movups  xmmword ptr [rcx+rax], xmm0
0x1004041e0  movups  xmm1, xmmword ptr [rbx+10h]
0x1004041e4  movups  xmmword ptr [rcx+rax+10h], xmm1
0x1004041e9  movups  xmm0, xmmword ptr [rbx+20h]
0x1004041ed  movups  xmmword ptr [rcx+rax+20h], xmm0
0x1004041f2  movups  xmm1, xmmword ptr [rbx+30h]
0x1004041f6  movups  xmmword ptr [rcx+rax+30h], xmm1
0x1004041fb  movups  xmm0, xmmword ptr [rbx+40h]
0x1004041ff  movups  xmmword ptr [rcx+rax+40h], xmm0
0x100404204  movups  xmm1, xmmword ptr [rbx+50h]
0x100404208  movups  xmmword ptr [rcx+rax+50h], xmm1
0x10040420d  movups  xmm0, xmmword ptr [rbx+60h]
0x100404211  movups  xmmword ptr [rcx+rax+60h], xmm0
0x100404216  movups  xmm1, xmmword ptr [rbx+70h]
0x10040421a  movups  xmmword ptr [rcx+rax+70h], xmm1
0x10040421f  movups  xmm0, xmmword ptr [rbx+80h]
0x100404226  movups  xmmword ptr [rcx+rax+80h], xmm0
0x10040422e  movsd   xmm1, qword ptr [rbx+90h]
0x100404236  movsd   qword ptr [rcx+rax+90h], xmm1
0x10040423f  dec     dword ptr [rdi+0B18h]
0x100404245  jmp     loc_1004040B1
0x10040424a  mov     eax, [rbx+18h]
0x10040424d  cmp     eax, cs:dword_100450B48
0x100404253  jnz     short loc_100404295
0x100404255  mov     rdx, cs:?xmlns@CodeStringPtr@@2UStringPtr@@A; Buf2
0x10040425c  mov     r8d, eax
0x10040425f  mov     rcx, [rbx+10h]; Buf1
0x100404263  add     r8, r8; Size
0x100404266  call    memcmp
0x10040426b  test    eax, eax
0x10040426d  jnz     short loc_100404295
0x10040426f  mov     rax, [rbx]
0x100404272  lea     rcx, [r14+1]
0x100404276  lea     rdx, [rsp+48h+var_28]
0x10040427b  lea     rcx, [rax+rcx*2]
0x10040427f  mov     eax, [rbx+8]
0x100404282  sub     eax, r14d
0x100404285  mov     qword ptr [rsp+48h+var_28], rcx
0x10040428a  dec     eax
0x10040428c  mov     dword ptr [rsp+48h+var_28+8], eax
0x100404290  jmp     loc_10040417D
0x100404295  mov     [rbx+64h], r15d
0x100404299  jmp     loc_1004040B1
0x10040429e  mov     dword ptr [rdi+6F0h], 1
0x1004042a8  lea     rax, ?ParseEETagEnd@YReader@@AEAAXXZ; YReader::ParseEETagEnd(void)
0x1004042af  jmp     short loc_1004042C2
0x1004042b1  mov     dword ptr [rdi+6F0h], 2
0x1004042bb  lea     rax, ?ParseTagEnd@YReader@@AEAAXXZ; YReader::ParseTagEnd(void)
0x1004042c2  mov     r14, [rsp+48h+var_18]
0x1004042c7  mov     rsi, [rsp+48h+arg_10]
0x1004042cc  mov     rbp, [rsp+48h+arg_8]
0x1004042d1  mov     rbx, [rsp+48h+arg_0]
0x1004042d6  mov     qword ptr [rsp+48h+var_28], rax
0x1004042db  mov     dword ptr [rsp+48h+var_28+8], r15d
0x1004042e0  movups  xmm0, [rsp+48h+var_28]
0x1004042e5  movups  xmmword ptr [rdi+5E0h], xmm0
0x1004042ec  add     rsp, 38h
0x1004042f0  pop     r15
0x1004042f2  pop     rdi
0x1004042f3  retn
0x1004042f4  mov     ecx, 0C00CEE01h; int
0x1004042f9  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
