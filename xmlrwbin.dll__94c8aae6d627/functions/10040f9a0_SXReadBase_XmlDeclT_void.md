# SXReadBase::XmlDeclT(void)

- ea: `0x10040f9a0`
- end: `0x10040fbe3`
- name: `?XmlDeclT@SXReadBase@@IEAAXXZ`
- size: `579`
- prototype: `void __fastcall(SXReadBase *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x10040edb0`

## callees

- `0x100401350`
- `0x100406be0`
- `0x10040f9a0`
- `0x100410e60`
- `0x100411000`
- `0x100411160`

## pseudocode

```c
void __fastcall SXReadBase::XmlDeclT(SXReadBase *this)
{
  unsigned int Mb32; // eax
  unsigned __int64 v3; // r14
  unsigned int v4; // esi
  unsigned int v5; // eax
  wchar_t *WCharBuffer; // rdi
  char *v7; // rcx
  __int64 v8; // rdx
  signed __int64 v9; // rdi
  __int16 v10; // ax
  char *v11; // rax
  unsigned int v12; // edi
  __int64 v13; // rax
  _BYTE *v14; // rax
  unsigned int v15; // esi
  unsigned int v16; // eax
  unsigned __int8 *v17; // rax
  unsigned __int8 *v18; // rax
  int v19; // ecx
  __int128 v20; // xmm0

  Mb32 = SXReadBase::GetMb32(this);
  v3 = Mb32;
  v4 = 2 * Mb32;
  if ( 2 * Mb32 < Mb32 )
    goto LABEL_36;
  v5 = *((_DWORD *)this + 174);
  if ( v5 && v4 > v5 )
    goto LABEL_39;
  _mm_lfence();
  if ( v4 )
  {
    WCharBuffer = SXReadBase::GetWCharBuffer(this, 0, v3);
    SXReadBase::GetBytes(this, (unsigned __int8 *)WCharBuffer, v4);
  }
  else
  {
    WCharBuffer = SXReadBase::GetWCharBuffer(this, 0, 2u);
  }
  v7 = (char *)this + 656;
  if ( v3 > 0x7FFFFFFE )
  {
    *(_WORD *)v7 = 0;
    goto LABEL_38;
  }
  v8 = 16;
  v9 = (char *)WCharBuffer - v7;
  do
  {
    if ( !(v8 + v3 - 16) )
      break;
    v10 = *(_WORD *)&v7[v9];
    if ( !v10 )
      break;
    *(_WORD *)v7 = v10;
    v7 += 2;
    --v8;
  }
  while ( v8 );
  v11 = v7 - 2;
  if ( v8 )
    v11 = v7;
  v12 = 0;
  *(_WORD *)v11 = 0;
  if ( !v8 )
  {
LABEL_38:
    MXRRaiseException(-2147467259);
    __debugbreak();
  }
  v13 = *((_QWORD *)this + 179);
  *((_DWORD *)this + 172) = v3;
  if ( *((_QWORD *)this + 178) != v13 || (_mm_lfence(), SXReadBase::Pull(this)) )
  {
    _mm_lfence();
    v14 = (_BYTE *)*((_QWORD *)this + 178);
    if ( *v14 == 0xFD )
    {
      if ( v14 == *((_BYTE **)this + 179) )
      {
        _mm_lfence();
        if ( !SXReadBase::Pull(this) )
          goto LABEL_38;
      }
      ++*((_QWORD *)this + 178);
      _mm_lfence();
      v12 = SXReadBase::GetMb32(this);
      v15 = 2 * v12;
      if ( 2 * v12 >= v12 )
      {
        v16 = *((_DWORD *)this + 174);
        if ( !v16 || v15 <= v16 )
        {
          _mm_lfence();
          if ( v15 )
          {
            v17 = (unsigned __int8 *)SXReadBase::GetWCharBuffer(this, -1, v12);
            *((_QWORD *)this + 142) = v17;
            SXReadBase::GetBytes(this, v17, v15);
          }
          else
          {
            *((_QWORD *)this + 142) = SXReadBase::GetWCharBuffer(this, -1, 2u);
          }
          goto LABEL_27;
        }
LABEL_39:
        MXRRaiseException(-1072897499);
        JUMPOUT(0x10040FBE2LL);
      }
LABEL_36:
      MXRRaiseException(-2147352566);
      __debugbreak();
    }
  }
  *((_QWORD *)this + 142) = 0;
LABEL_27:
  *((_DWORD *)this + 286) = v12;
  if ( *((_QWORD *)this + 178) == *((_QWORD *)this + 179) )
  {
    _mm_lfence();
    if ( !SXReadBase::Pull(this) )
      goto LABEL_38;
  }
  _mm_lfence();
  v18 = (unsigned __int8 *)*((_QWORD *)this + 178);
  v19 = *v18;
  *((_QWORD *)this + 178) = v18 + 1;
  if ( !(_BYTE)v19 )
  {
    v20 = *(_OWORD *)&CodeStringPtr::empty;
    goto LABEL_33;
  }
  if ( v19 == 1 )
  {
    v20 = CodeStringPtr::yes;
    goto LABEL_33;
  }
  if ( v19 != 2 )
    goto LABEL_38;
  v20 = CodeStringPtr::no;
LABEL_33:
  *((_OWORD *)this + 40) = v20;
}

```

## disassembly

```asm
0x10040f9a0  mov     [rsp+arg_0], rbx
0x10040f9a5  mov     [rsp+arg_8], rsi
0x10040f9aa  mov     [rsp+arg_10], rdi
0x10040f9af  push    r14
0x10040f9b1  sub     rsp, 20h
0x10040f9b5  mov     rbx, rcx
0x10040f9b8  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x10040f9bd  mov     r14d, eax
0x10040f9c0  lea     esi, [r14+r14]
0x10040f9c4  cmp     esi, eax
0x10040f9c6  jb      loc_10040FBBD
0x10040f9cc  mov     eax, [rbx+2B8h]
0x10040f9d2  test    eax, eax
0x10040f9d4  jz      short loc_10040F9DE
0x10040f9d6  cmp     esi, eax
0x10040f9d8  ja      loc_10040FBD8
0x10040f9de  lfence
0x10040f9e1  xor     edx, edx; int
0x10040f9e3  mov     rcx, rbx; this
0x10040f9e6  test    esi, esi
0x10040f9e8  jz      short loc_10040FA05
0x10040f9ea  mov     r8d, r14d; unsigned int
0x10040f9ed  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x10040f9f2  mov     r8d, esi; unsigned int
0x10040f9f5  mov     rdx, rax; unsigned __int8 *
0x10040f9f8  mov     rcx, rbx; this
0x10040f9fb  mov     rdi, rax
0x10040f9fe  call    ?GetBytes@SXReadBase@@IEAAXPEAEK@Z; SXReadBase::GetBytes(uchar *,ulong)
0x10040fa03  jmp     short loc_10040FA13
0x10040fa05  mov     r8d, 2; unsigned int
0x10040fa0b  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x10040fa10  mov     rdi, rax
0x10040fa13  lea     rcx, [rbx+290h]
0x10040fa1a  cmp     r14, 7FFFFFFEh
0x10040fa21  ja      loc_10040FBC8
0x10040fa27  mov     edx, 10h
0x10040fa2c  sub     rdi, rcx
0x10040fa2f  nop
0x10040fa30  lea     rax, [r14-10h]
0x10040fa34  add     rax, rdx
0x10040fa37  jz      short loc_10040FA4F
0x10040fa39  movzx   eax, word ptr [rdi+rcx]
0x10040fa3d  test    ax, ax
0x10040fa40  jz      short loc_10040FA4F
0x10040fa42  mov     [rcx], ax
0x10040fa45  add     rcx, 2
0x10040fa49  sub     rdx, 1
0x10040fa4d  jnz     short loc_10040FA30
0x10040fa4f  test    rdx, rdx
0x10040fa52  lea     rax, [rcx-2]
0x10040fa56  cmovnz  rax, rcx
0x10040fa5a  xor     edi, edi
0x10040fa5c  mov     [rax], di
0x10040fa5f  test    rdx, rdx
0x10040fa62  jz      loc_10040FBCD
0x10040fa68  mov     rax, [rbx+598h]
0x10040fa6f  mov     [rbx+2B0h], r14d
0x10040fa76  cmp     [rbx+590h], rax
0x10040fa7d  jnz     short loc_10040FA92
0x10040fa7f  lfence
0x10040fa82  mov     rcx, rbx; this
0x10040fa85  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x10040fa8a  test    al, al
0x10040fa8c  jz      loc_10040FB34
0x10040fa92  lfence
0x10040fa95  mov     rax, [rbx+590h]
0x10040fa9c  cmp     byte ptr [rax], 0FDh
0x10040fa9f  jnz     loc_10040FB34
0x10040faa5  cmp     rax, [rbx+598h]
0x10040faac  jnz     short loc_10040FAC1
0x10040faae  lfence
0x10040fab1  mov     rcx, rbx; this
0x10040fab4  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x10040fab9  test    al, al
0x10040fabb  jz      loc_10040FBCD
0x10040fac1  inc     qword ptr [rbx+590h]
0x10040fac8  lfence
0x10040facb  mov     rcx, rbx; this
0x10040face  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x10040fad3  mov     edi, eax
0x10040fad5  lea     esi, [rax+rax]
0x10040fad8  cmp     esi, eax
0x10040fada  jb      loc_10040FBBD
0x10040fae0  mov     eax, [rbx+2B8h]
0x10040fae6  test    eax, eax
0x10040fae8  jz      short loc_10040FAF2
0x10040faea  cmp     esi, eax
0x10040faec  ja      loc_10040FBD8
0x10040faf2  lfence
0x10040faf5  mov     edx, 0FFFFFFFFh; int
0x10040fafa  mov     rcx, rbx; this
0x10040fafd  test    esi, esi
0x10040faff  jz      short loc_10040FB20
0x10040fb01  mov     r8d, edi; unsigned int
0x10040fb04  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x10040fb09  mov     r8d, esi; unsigned int
0x10040fb0c  mov     [rbx+470h], rax
0x10040fb13  mov     rdx, rax; unsigned __int8 *
0x10040fb16  mov     rcx, rbx; this
0x10040fb19  call    ?GetBytes@SXReadBase@@IEAAXPEAEK@Z; SXReadBase::GetBytes(uchar *,ulong)
0x10040fb1e  jmp     short loc_10040FB3B
0x10040fb20  mov     r8d, 2; unsigned int
0x10040fb26  call    ?GetWCharBuffer@SXReadBase@@IEAAPEA_WHK@Z; SXReadBase::GetWCharBuffer(int,ulong)
0x10040fb2b  mov     [rbx+470h], rax
0x10040fb32  jmp     short loc_10040FB3B
0x10040fb34  mov     [rbx+470h], rdi
0x10040fb3b  mov     [rbx+478h], edi
0x10040fb41  mov     rax, [rbx+598h]
0x10040fb48  cmp     [rbx+590h], rax
0x10040fb4f  jnz     short loc_10040FB60
0x10040fb51  lfence
0x10040fb54  mov     rcx, rbx; this
0x10040fb57  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x10040fb5c  test    al, al
0x10040fb5e  jz      short loc_10040FBCD
0x10040fb60  lfence
0x10040fb63  mov     rax, [rbx+590h]
0x10040fb6a  movzx   ecx, byte ptr [rax]
0x10040fb6d  inc     rax
0x10040fb70  mov     [rbx+590h], rax
0x10040fb77  mov     edx, ecx
0x10040fb79  test    cl, cl
0x10040fb7b  jz      short loc_10040FBB4
0x10040fb7d  sub     edx, 1
0x10040fb80  jz      short loc_10040FBAB
0x10040fb82  cmp     edx, 1
0x10040fb85  jnz     short loc_10040FBCD
0x10040fb87  movups  xmm0, xmmword ptr cs:?no@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::no
0x10040fb8e  mov     rsi, [rsp+28h+arg_8]
0x10040fb93  mov     rdi, [rsp+28h+arg_10]
0x10040fb98  movups  xmmword ptr [rbx+280h], xmm0
0x10040fb9f  mov     rbx, [rsp+28h+arg_0]
0x10040fba4  add     rsp, 20h
0x10040fba8  pop     r14
0x10040fbaa  retn
0x10040fbab  movups  xmm0, xmmword ptr cs:?yes@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::yes
0x10040fbb2  jmp     short loc_10040FB8E
0x10040fbb4  movups  xmm0, xmmword ptr cs:?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x10040fbbb  jmp     short loc_10040FB8E
0x10040fbbd  mov     ecx, 8002000Ah; int
0x10040fbc2  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040fbc7  int     3; Trap to Debugger
0x10040fbc8  xor     edi, edi
0x10040fbca  mov     [rcx], di
0x10040fbcd  mov     ecx, 80004005h; int
0x10040fbd2  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040fbd7  int     3; Trap to Debugger
0x10040fbd8  mov     ecx, 0C00CE225h; int
0x10040fbdd  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
