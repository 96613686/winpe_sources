# SXReadBase::ReadAttributeValueSizeAndType(void)

- ea: `0x10040f700`
- end: `0x10040f99a`
- name: `?ReadAttributeValueSizeAndType@SXReadBase@@IEAA_NXZ`
- size: `666`
- prototype: `bool __fastcall(SXReadBase *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x100405a70`

## callees

- `0x100401350`
- `0x100406be0`
- `0x100407050`
- `0x10040f700`
- `0x10040ff60`
- `0x100410010`
- `0x100411160`
- `0x100424580`

## pseudocode

```c
bool __fastcall SXReadBase::ReadAttributeValueSizeAndType(SXReadBase *this)
{
  unsigned __int8 *v2; // rax
  unsigned __int8 v3; // di
  unsigned int Mb32; // edi
  __int64 v5; // rcx
  unsigned int v6; // edx
  __int64 v7; // rcx
  bool result; // al
  unsigned int v9; // eax
  int v10; // ecx
  unsigned int v11; // eax

  while ( 2 )
  {
    if ( *((_QWORD *)this + 178) != *((_QWORD *)this + 179) || SXReadBase::Pull(this) )
    {
      v2 = (unsigned __int8 *)*((_QWORD *)this + 178);
      v3 = *v2;
      if ( *v2 == 0xF6 )
        return 0;
    }
    else
    {
      v2 = (unsigned __int8 *)*((_QWORD *)this + 178);
      v3 = 0;
    }
    if ( v2 == *((unsigned __int8 **)this + 179) && !SXReadBase::Pull(this) )
    {
LABEL_38:
      MXRRaiseException(-2147467259);
      __debugbreak();
    }
    ++*((_QWORD *)this + 178);
    switch ( v3 )
    {
      case 0x8Cu:
        *((_DWORD *)this + 305) = 140;
        return 1;
      case 0xE9u:
        v7 = *((_QWORD *)this + 90);
        if ( v7 )
        {
          *((_QWORD *)this + 90) = *(_QWORD *)(v7 + 168);
          (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
        }
        else
        {
          *((_QWORD *)this + 90) = 0;
        }
        SXTokenTable::PushTokenTable(*((struct IMalloc **)this + 1), (struct SXTokenTable **)this + 90);
        continue;
      case 0xEAu:
        Mb32 = SXReadBase::GetMb32(this);
        if ( Mb32 )
        {
          while ( 1 )
          {
            v5 = Mb32;
            v6 = *((_DWORD *)this + 358) - *((_DWORD *)this + 356);
            if ( v6 < Mb32 )
              v5 = v6;
            *((_QWORD *)this + 178) += v5;
            Mb32 -= v5;
            if ( !Mb32 )
              break;
            if ( !SXReadBase::Pull(this) )
            {
              MXRRaiseException(-1072896679);
              __debugbreak();
            }
          }
        }
        continue;
      case 0xEFu:
        SXReadBase::TokenT(this);
        continue;
      case 0xF0u:
        SXReadBase::NameT(this);
        continue;
      case 0xF5u:
        return 0;
      default:
        if ( (unsigned __int8)(v3 - 1) > 0x1Au && (unsigned __int8)(v3 + 0x80) > 0xDu
          || ((v3 - 21) & 0xFA) == 0 && v3 != 22 )
        {
          goto LABEL_38;
        }
        v9 = v3 - 100;
        if ( v3 < 0x80u )
          v9 = v3;
        if ( v9 >= 0x2A )
          goto LABEL_38;
        v10 = *((unsigned __int8 *)&SXFormatDataByType + 8 * (int)v9);
        if ( (v10 & 0x40) != 0 )
        {
          if ( v10 == 65 )
          {
            v11 = SXReadBase::GetMb32(this);
            v10 = 2 * v11;
            if ( v11 > 2 * v11 )
            {
              MXRRaiseException(-2147352566);
              __debugbreak();
            }
          }
          else
          {
            v10 = SXReadBase::GetMb32(this);
          }
        }
        *((_DWORD *)this + 326) = v10;
        result = 1;
        *((_DWORD *)this + 305) = v3;
        break;
    }
    return result;
  }
}

```

## disassembly

```asm
0x10040f700  mov     [rsp+arg_8], rbx
0x10040f705  mov     [rsp+arg_10], rbp
0x10040f70a  push    rdi
0x10040f70b  sub     rsp, 20h
0x10040f70f  mov     rbx, rcx
0x10040f712  mov     [rsp+28h+arg_0], rsi
0x10040f717  lea     rbp, __ImageBase
0x10040f71e  xchg    ax, ax
0x10040f720  mov     rax, [rbx+598h]
0x10040f727  cmp     [rbx+590h], rax
0x10040f72e  jnz     short loc_10040F748
0x10040f730  mov     rcx, rbx; this
0x10040f733  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x10040f738  test    al, al
0x10040f73a  jnz     short loc_10040F748
0x10040f73c  mov     rax, [rbx+590h]
0x10040f743  xor     dil, dil
0x10040f746  jmp     short loc_10040F75C
0x10040f748  mov     rax, [rbx+590h]
0x10040f74f  movzx   edi, byte ptr [rax]
0x10040f752  cmp     dil, 0F6h
0x10040f756  jz      loc_10040F8D9; jumptable 000000010040F7A3 case 245
0x10040f75c  cmp     rax, [rbx+598h]
0x10040f763  jnz     short loc_10040F775
0x10040f765  mov     rcx, rbx; this
0x10040f768  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x10040f76d  test    al, al
0x10040f76f  jz      loc_10040F906
0x10040f775  inc     qword ptr [rbx+590h]
0x10040f77c  movzx   esi, dil
0x10040f780  lea     eax, [rsi-8Ch]; switch 106 cases
0x10040f786  cmp     eax, 69h
0x10040f789  ja      def_10040F7A3; jumptable 000000010040F7A3 default case, cases 141-232,235-238,241-244
0x10040f78f  cdqe
0x10040f791  movzx   eax, ds:(byte_10040F930 - 100400000h)[rax+rbp]
0x10040f799  mov     ecx, ss:(jpt_10040F7A3 - 100400000h)[rbp+rax*4]
0x10040f7a0  add     rcx, rbp
0x10040f7a3  jmp     rcx; switch jump
0x10040f7a5  mov     rcx, rbx; jumptable 000000010040F7A3 case 240
0x10040f7a8  call    ?NameT@SXReadBase@@IEAAXXZ; SXReadBase::NameT(void)
0x10040f7ad  jmp     loc_10040F720
0x10040f7b2  mov     rcx, rbx; jumptable 000000010040F7A3 case 239
0x10040f7b5  call    ?TokenT@SXReadBase@@IEAAXXZ; SXReadBase::TokenT(void)
0x10040f7ba  jmp     loc_10040F720
0x10040f7bf  mov     rcx, rbx; jumptable 000000010040F7A3 case 234
0x10040f7c2  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x10040f7c7  mov     edi, eax
0x10040f7c9  test    eax, eax
0x10040f7cb  jz      loc_10040F720
0x10040f7d1  nop     dword ptr [rax+00h]
0x10040f7d5  nop     word ptr [rax+rax+00000000h]
0x10040f7e0  mov     edx, [rbx+598h]
0x10040f7e6  mov     ecx, edi
0x10040f7e8  sub     edx, [rbx+590h]
0x10040f7ee  cmp     edx, edi
0x10040f7f0  cmovb   ecx, edx
0x10040f7f3  add     [rbx+590h], rcx
0x10040f7fa  sub     edi, ecx
0x10040f7fc  jz      loc_10040F720
0x10040f802  mov     rcx, rbx; this
0x10040f805  call    ?Pull@SXReadBase@@AEAA_NXZ; SXReadBase::Pull(void)
0x10040f80a  test    al, al
0x10040f80c  jz      loc_10040F8F0
0x10040f812  jmp     short loc_10040F7E0
0x10040f814  mov     rcx, [rbx+2D0h]; jumptable 000000010040F7A3 case 233
0x10040f81b  test    rcx, rcx
0x10040f81e  jz      short loc_10040F841
0x10040f820  mov     rax, [rcx+0A8h]
0x10040f827  mov     edx, 1
0x10040f82c  mov     [rbx+2D0h], rax
0x10040f833  mov     rax, [rcx]
0x10040f836  mov     rax, [rax]
0x10040f839  call    cs:__guard_dispatch_icall_fptr
0x10040f83f  jmp     short loc_10040F84C
0x10040f841  mov     qword ptr [rbx+2D0h], 0
0x10040f84c  mov     rcx, [rbx+8]; struct IMalloc *
0x10040f850  lea     rdx, [rbx+2D0h]; struct SXTokenTable **
0x10040f857  call    ?PushTokenTable@SXTokenTable@@SAXPEAUIMalloc@@PEAPEAV1@@Z; SXTokenTable::PushTokenTable(IMalloc *,SXTokenTable * *)
0x10040f85c  jmp     loc_10040F720
0x10040f861  mov     dword ptr [rbx+4C4h], 8Ch; jumptable 000000010040F7A3 case 140
0x10040f86b  mov     al, 1
0x10040f86d  jmp     short loc_10040F8DB
0x10040f86f  lea     eax, [rdi-1]; jumptable 000000010040F7A3 default case, cases 141-232,235-238,241-244
0x10040f872  cmp     al, 1Ah
0x10040f874  jbe     short loc_10040F881
0x10040f876  lea     eax, [rdi-80h]
0x10040f879  cmp     al, 0Dh
0x10040f87b  ja      loc_10040F906
0x10040f881  lea     eax, [rdi-15h]
0x10040f884  test    al, 0FAh
0x10040f886  jnz     short loc_10040F88E
0x10040f888  cmp     dil, 16h
0x10040f88c  jnz     short loc_10040F906
0x10040f88e  cmp     dil, 80h
0x10040f892  lea     eax, [rsi-64h]
0x10040f895  cmovb   eax, esi
0x10040f898  cmp     eax, 2Ah ; '*'
0x10040f89b  jnb     short loc_10040F906
0x10040f89d  cdqe
0x10040f89f  movzx   ecx, ss:rva ?SXFormatDataByType@@3PAUSXFORMATTYPEDATA@@A[rbp+rax*8]; SXFORMATTYPEDATA near * SXFormatDataByType ...
0x10040f8a7  test    cl, 40h
0x10040f8aa  jz      short loc_10040F8C9
0x10040f8ac  cmp     ecx, 41h ; 'A'
0x10040f8af  mov     rcx, rbx; this
0x10040f8b2  jnz     short loc_10040F8C2
0x10040f8b4  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x10040f8b9  lea     ecx, [rax+rax]
0x10040f8bc  cmp     eax, ecx
0x10040f8be  ja      short loc_10040F8FB
0x10040f8c0  jmp     short loc_10040F8C9
0x10040f8c2  call    ?GetMb32@SXReadBase@@IEAAKXZ; SXReadBase::GetMb32(void)
0x10040f8c7  mov     ecx, eax
0x10040f8c9  mov     [rbx+518h], ecx
0x10040f8cf  mov     al, 1
0x10040f8d1  mov     [rbx+4C4h], esi
0x10040f8d7  jmp     short loc_10040F8DB
0x10040f8d9  xor     al, al; jumptable 000000010040F7A3 case 245
0x10040f8db  mov     rsi, [rsp+28h+arg_0]
0x10040f8e0  mov     rbx, [rsp+28h+arg_8]
0x10040f8e5  mov     rbp, [rsp+28h+arg_10]
0x10040f8ea  add     rsp, 20h
0x10040f8ee  pop     rdi
0x10040f8ef  retn
0x10040f8f0  mov     ecx, 0C00CE559h; int
0x10040f8f5  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040f8fa  int     3; Trap to Debugger
0x10040f8fb  mov     ecx, 8002000Ah; int
0x10040f900  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040f905  int     3; Trap to Debugger
0x10040f906  mov     ecx, 80004005h; int
0x10040f90b  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040f910  int     3; Trap to Debugger
```
