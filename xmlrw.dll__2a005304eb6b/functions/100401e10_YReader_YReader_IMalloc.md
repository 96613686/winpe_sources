# YReader::YReader(IMalloc *)

- ea: `0x100401e10`
- end: `0x100402493`
- name: `??0YReader@@QEAA@PEAUIMalloc@@@Z`
- size: `1667`
- prototype: `YReader *__fastcall(YReader *__hidden this, struct IMalloc *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x100401bd0`

## callees

- `0x100401e10`
- `0x1004277a0`
- `0x100439df0`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x100402462`
- `KERNEL32!EnterCriticalSection` at `0x100402462`
- `KERNEL32!LeaveCriticalSection` at `0x100402475`
- `KERNEL32!LeaveCriticalSection` at `0x100402475`
- `KERNEL32!GetTickCount` at `0x100402443`
- `KERNEL32!GetTickCount` at `0x100402443`

## pseudocode

```c
YReader *__fastcall YReader::YReader(YReader *this, struct IMalloc *a2)
{
  __int64 v4; // rbx
  char *v5; // rcx
  __int64 v6; // rdx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  __int128 v10; // xmm0
  __int128 v11; // xmm0
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  DWORD TickCount; // eax
  __int128 v18; // [rsp+20h] [rbp-18h]

  *((_QWORD *)this + 1) = a2;
  *(_QWORD *)this = &YReader::`vftable'{for `Base'};
  *((_QWORD *)this + 8) = a2;
  *((_QWORD *)this + 2) = &YReader::`vftable'{for `IInfoSetEntityLocator'};
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 3) = &YReader::`vftable'{for `ISupportErrorInfo'};
  *((_DWORD *)this + 21) = 2;
  *((_QWORD *)this + 4) = &YReader::`vftable'{for `IInfoSetReader'};
  *((_QWORD *)this + 6) = a2;
  *((_QWORD *)this + 5) = &Scanner::`vftable';
  *((_QWORD *)this + 7) = &_stack<CharacterSource *,2>::`vftable';
  *((_QWORD *)this + 9) = (char *)this + 88;
  *(_OWORD *)((char *)this + 88) = 0;
  *((_QWORD *)this + 16) = a2;
  *((_QWORD *)this + 15) = &_stack<unsigned int,16>::`vftable';
  *((_QWORD *)this + 17) = (char *)this + 152;
  *((_DWORD *)this + 36) = 0;
  *((_DWORD *)this + 37) = 8;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 0;
  *(_OWORD *)((char *)this + 152) = 0;
  *(_OWORD *)((char *)this + 168) = 0;
  *(_OWORD *)((char *)this + 184) = 0;
  *(_OWORD *)((char *)this + 200) = 0;
  *((_QWORD *)this + 30) = a2;
  *((_QWORD *)this + 29) = &_stack<wchar_t,2>::`vftable';
  *((_QWORD *)this + 31) = (char *)this + 264;
  *((_DWORD *)this + 64) = 0;
  *((_DWORD *)this + 65) = 2;
  *((_QWORD *)this + 27) = 0;
  *((_WORD *)this + 112) = 0;
  *((_DWORD *)this + 66) = 0;
  *((_QWORD *)this + 41) = Scanner::ScanNameN;
  *((_QWORD *)this + 42) = Scanner::ScanNameQualifiedN;
  *((_QWORD *)this + 43) = &Scanner::AutodetectInput::`vftable';
  *((_DWORD *)this + 78) = 0;
  *((_WORD *)this + 158) = 1;
  *((_DWORD *)this + 80) = 0;
  *((_QWORD *)this + 44) = a2;
  *((_QWORD *)this + 45) = 0;
  *((_DWORD *)this + 92) = 0;
  *((_QWORD *)this + 53) = *((_QWORD *)this + 1);
  *((_QWORD *)this + 52) = &BlockAlloc::`vftable';
  *((_QWORD *)this + 54) = 0;
  *((_QWORD *)this + 55) = 0;
  *((_QWORD *)this + 57) = *((_QWORD *)this + 1);
  *((_QWORD *)this + 56) = &_stack<DeclAttDef *,4>::`vftable';
  *((_QWORD *)this + 58) = (char *)this + 480;
  *((_DWORD *)this + 118) = 0;
  *((_DWORD *)this + 119) = 4;
  *((_OWORD *)this + 30) = 0;
  *((_OWORD *)this + 31) = 0;
  v4 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 65) = v4;
  *((_QWORD *)this + 64) = &NamespaceSupport::`vftable';
  *((_QWORD *)this + 68) = v4;
  *((_DWORD *)this + 140) = 0;
  v5 = (char *)this + 568;
  *((_QWORD *)this + 67) = &_stack<NamespaceSupport::Map,16>::`vftable';
  *((_QWORD *)this + 69) = v5;
  *((_DWORD *)this + 141) = 16;
  memset(v5, 0, 0x280u);
  *((_QWORD *)this + 152) = v4;
  *((_QWORD *)this + 151) = &_dict<unsigned int,0>::`vftable';
  *((_QWORD *)this + 153) = 0;
  *((_DWORD *)this + 309) = 0;
  v6 = *((_QWORD *)this + 1);
  *((_QWORD *)this + 157) = &DeclExternalId::`vftable';
  *((_QWORD *)this + 158) = v6;
  *((_QWORD *)this + 159) = 0;
  *((_DWORD *)this + 320) = 0;
  v7 = dword_100450B38;
  *((_QWORD *)this + 161) = CodeStringPtr::empty;
  *((_DWORD *)this + 324) = v7;
  v8 = dword_100450B38;
  *((_QWORD *)this + 163) = CodeStringPtr::empty;
  *((_DWORD *)this + 328) = v8;
  v9 = dword_100450B38;
  *((_QWORD *)this + 165) = CodeStringPtr::empty;
  *((_QWORD *)this + 157) = &DeclDoctype::`vftable';
  *((_QWORD *)this + 167) = &_htable<DeclNotation>::`vftable';
  *((_QWORD *)this + 172) = &_htable<DeclNotation>::`vftable';
  *((_QWORD *)this + 177) = &_htable<DeclNotation>::`vftable';
  *((_QWORD *)this + 182) = &_htable<DeclNotation>::`vftable';
  *((_DWORD *)this + 332) = v9;
  *((_QWORD *)this + 168) = v6;
  *((_QWORD *)this + 169) = 0;
  *((_DWORD *)this + 340) = 0;
  *((_QWORD *)this + 173) = v6;
  *((_QWORD *)this + 174) = 0;
  *((_DWORD *)this + 350) = 0;
  *((_QWORD *)this + 178) = v6;
  *((_QWORD *)this + 179) = 0;
  *((_DWORD *)this + 360) = 0;
  *((_QWORD *)this + 183) = v6;
  *((_QWORD *)this + 184) = 0;
  *((_DWORD *)this + 370) = 0;
  *((_QWORD *)this + 187) = 0;
  *(_QWORD *)&v18 = YReader::ParseError;
  DWORD2(v18) = 0;
  v10 = v18;
  *(_QWORD *)&v18 = YReader::ParseElementN;
  DWORD2(v18) = 0;
  *((_OWORD *)this + 94) = v10;
  v11 = v18;
  *(_QWORD *)&v18 = YReader::ParseAttributesN;
  DWORD2(v18) = 0;
  *((_OWORD *)this + 96) = v11;
  *((_OWORD *)this + 97) = v18;
  *((_QWORD *)this + 196) = 0;
  *((_DWORD *)this + 394) = 0;
  *((_QWORD *)this + 198) = 0;
  *((_DWORD *)this + 398) = 0;
  *((_QWORD *)this + 200) = 0;
  *((_DWORD *)this + 402) = 0;
  *((_QWORD *)this + 202) = 0;
  *((_DWORD *)this + 406) = 0;
  *((_QWORD *)this + 204) = 0;
  *((_DWORD *)this + 410) = 0;
  *((_QWORD *)this + 206) = 0;
  *((_DWORD *)this + 414) = 0;
  *((_QWORD *)this + 208) = 0;
  *((_DWORD *)this + 418) = 0;
  *((_QWORD *)this + 210) = 0;
  *((_DWORD *)this + 422) = 0;
  *((_QWORD *)this + 212) = 0;
  *((_DWORD *)this + 426) = 0;
  v12 = dword_100450B38;
  *((_QWORD *)this + 214) = CodeStringPtr::empty;
  *((_DWORD *)this + 430) = v12;
  v13 = dword_100450B38;
  *((_QWORD *)this + 216) = CodeStringPtr::empty;
  *((_DWORD *)this + 434) = v13;
  v14 = dword_100450B38;
  *((_QWORD *)this + 218) = CodeStringPtr::empty;
  *((_DWORD *)this + 438) = v14;
  v15 = dword_100450B38;
  *((_QWORD *)this + 220) = CodeStringPtr::empty;
  *((_DWORD *)this + 442) = v15;
  *((_QWORD *)this + 234) = *((_QWORD *)this + 1);
  *((_QWORD *)this + 233) = &_stack<YReader::Element,16>::`vftable';
  *((_DWORD *)this + 444) = 0;
  *(_QWORD *)((char *)this + 1780) = 1;
  *(_QWORD *)((char *)this + 1788) = 0;
  *((_BYTE *)this + 1796) = 1;
  *((_QWORD *)this + 229) = 0;
  *((_QWORD *)this + 230) = 0;
  *((_DWORD *)this + 464) = 0;
  *((_QWORD *)this + 235) = (char *)this + 1896;
  *((_DWORD *)this + 472) = 0;
  *((_DWORD *)this + 473) = 16;
  memset((char *)this + 1896, 0, 0x380u);
  *((_QWORD *)this + 353) = *((_QWORD *)this + 1);
  *((_QWORD *)this + 354) = (char *)this + 2848;
  *((_QWORD *)this + 349) = 0;
  *((_QWORD *)this + 350) = 0;
  *((_QWORD *)this + 352) = &_stack<Attribute,16>::`vftable';
  *((_DWORD *)this + 710) = 0;
  *((_DWORD *)this + 711) = 16;
  memset((char *)this + 2848, 0, 0x980u);
  *((_QWORD *)this + 661) = *((_QWORD *)this + 1);
  *((_QWORD *)this + 662) = (char *)this + 5312;
  *((_QWORD *)this + 660) = &_stack<Attribute,16>::`vftable';
  *((_DWORD *)this + 1326) = 0;
  *((_DWORD *)this + 1327) = 16;
  memset((char *)this + 5312, 0, 0x980u);
  *((_QWORD *)this + 969) = *((_QWORD *)this + 1);
  *((_QWORD *)this + 970) = (char *)this + 7776;
  *((_QWORD *)this + 968) = &_stack<AttValueToken,16>::`vftable';
  *((_DWORD *)this + 1942) = 0;
  *((_DWORD *)this + 1943) = 16;
  memset((char *)this + 7776, 0, 0x180u);
  *((_QWORD *)this + 1021) = *((_QWORD *)this + 1);
  *((_QWORD *)this + 1020) = &_stack<unsigned int,16>::`vftable';
  *((_QWORD *)this + 1022) = (char *)this + 0x2000;
  *((_DWORD *)this + 2046) = 0;
  *((_DWORD *)this + 2047) = 16;
  *((_OWORD *)this + 512) = 0;
  *((_OWORD *)this + 513) = 0;
  *((_OWORD *)this + 514) = 0;
  *((_OWORD *)this + 515) = 0;
  *((_QWORD *)this + 1032) = 0;
  *((_DWORD *)this + 2067) = 1;
  if ( a2 )
    ((void (__fastcall *)(struct IMalloc *))a2->lpVtbl->AddRef)(a2);
  TickCount = GetTickCount();
  *((_DWORD *)this + 702) = TickCount ^ ((TickCount ^ (TickCount << 7)) << 11);
  EnterCriticalSection(&s_cs);
  ++s_cComponents;
  LeaveCriticalSection(&s_cs);
  return this;
}

```

## disassembly

```asm
0x100401e10  mov     [rsp+arg_0], rbx
0x100401e15  mov     [rsp+arg_8], rbp
0x100401e1a  mov     [rsp+arg_10], rsi
0x100401e1f  push    rdi
0x100401e20  sub     rsp, 30h
0x100401e24  mov     [rcx+8], rdx
0x100401e28  lea     rax, ??_7YReader@@6BBase@@@; const YReader::`vftable'{for `Base'}
0x100401e2f  mov     [rcx], rax
0x100401e32  mov     rdi, rcx
0x100401e35  mov     [rcx+40h], rdx
0x100401e39  lea     rax, ??_7YReader@@6BIInfoSetEntityLocator@@@; const YReader::`vftable'{for `IInfoSetEntityLocator'}
0x100401e40  mov     [rcx+10h], rax
0x100401e44  xor     ebp, ebp
0x100401e46  mov     [rcx+50h], ebp
0x100401e49  lea     rax, ??_7YReader@@6BISupportErrorInfo@@@; const YReader::`vftable'{for `ISupportErrorInfo'}
0x100401e50  mov     [rcx+18h], rax
0x100401e54  xorps   xmm0, xmm0
0x100401e57  mov     dword ptr [rcx+54h], 2
0x100401e5e  lea     rax, ??_7YReader@@6BIInfoSetReader@@@; const YReader::`vftable'{for `IInfoSetReader'}
0x100401e65  mov     [rcx+20h], rax
0x100401e69  mov     rsi, rdx
0x100401e6c  mov     [rcx+30h], rdx
0x100401e70  lea     rax, ??_7Scanner@@6B@; const Scanner::`vftable'
0x100401e77  mov     [rcx+28h], rax
0x100401e7b  lea     rax, ??_7?$_stack@PEAVCharacterSource@@$01@@6B@; const _stack<CharacterSource *,2>::`vftable'
0x100401e82  mov     [rcx+38h], rax
0x100401e86  lea     rax, [rcx+58h]
0x100401e8a  mov     [rcx+48h], rax
0x100401e8e  movups  xmmword ptr [rax], xmm0
0x100401e91  mov     [rcx+80h], rdx
0x100401e98  lea     rax, ??_7?$_stack@I$0BA@@@6B@; const _stack<uint,16>::`vftable'
0x100401e9f  mov     [rcx+78h], rax
0x100401ea3  lea     rax, [rcx+98h]
0x100401eaa  mov     [rcx+88h], rax
0x100401eb1  mov     [rcx+90h], ebp
0x100401eb7  mov     dword ptr [rcx+94h], 8
0x100401ec1  mov     [rcx+68h], rbp
0x100401ec5  mov     [rcx+70h], ebp
0x100401ec8  movups  xmmword ptr [rax], xmm0
0x100401ecb  movups  xmmword ptr [rax+10h], xmm0
0x100401ecf  movups  xmmword ptr [rax+20h], xmm0
0x100401ed3  movups  xmmword ptr [rax+30h], xmm0
0x100401ed7  mov     [rcx+0F0h], rdx
0x100401ede  lea     rax, ??_7?$_stack@_W$01@@6B@; const _stack<wchar_t,2>::`vftable'
0x100401ee5  mov     [rcx+0E8h], rax
0x100401eec  lea     rax, [rcx+108h]
0x100401ef3  mov     [rcx+0F8h], rax
0x100401efa  mov     [rcx+100h], ebp
0x100401f00  mov     dword ptr [rcx+104h], 2
0x100401f0a  mov     [rcx+0D8h], rbp
0x100401f11  mov     [rcx+0E0h], bp
0x100401f18  xor     ecx, ecx
0x100401f1a  mov     [rax], ecx
0x100401f1c  lea     rax, ?ScanNameN@Scanner@@AEAAXXZ; Scanner::ScanNameN(void)
0x100401f23  mov     [rdi+148h], rax
0x100401f2a  lea     rax, ?ScanNameQualifiedN@Scanner@@AEAAXXZ; Scanner::ScanNameQualifiedN(void)
0x100401f31  mov     [rdi+150h], rax
0x100401f38  lea     rax, ??_7AutodetectInput@Scanner@@6B@; const Scanner::AutodetectInput::`vftable'
0x100401f3f  mov     [rdi+158h], rax
0x100401f46  mov     [rdi+138h], ebp
0x100401f4c  mov     word ptr [rdi+13Ch], 1
0x100401f55  mov     [rdi+140h], ebp
0x100401f5b  mov     [rdi+160h], rdx
0x100401f62  mov     [rdi+168h], rbp
0x100401f69  mov     [rdi+170h], ebp
0x100401f6f  mov     rax, [rdi+8]
0x100401f73  mov     [rdi+1A8h], rax
0x100401f7a  lea     rax, ??_7BlockAlloc@@6B@; const BlockAlloc::`vftable'
0x100401f81  mov     [rdi+1A0h], rax
0x100401f88  mov     [rdi+1B0h], rbp
0x100401f8f  mov     [rdi+1B8h], rbp
0x100401f96  mov     rax, [rdi+8]
0x100401f9a  mov     [rdi+1C8h], rax
0x100401fa1  lea     rax, ??_7?$_stack@PEAVDeclAttDef@@$03@@6B@; const _stack<DeclAttDef *,4>::`vftable'
0x100401fa8  mov     [rdi+1C0h], rax
0x100401faf  lea     rax, [rdi+1E0h]
0x100401fb6  mov     [rdi+1D0h], rax
0x100401fbd  mov     [rdi+1D8h], ebp
0x100401fc3  mov     dword ptr [rdi+1DCh], 4
0x100401fcd  movups  xmmword ptr [rax], xmm0
0x100401fd0  movups  xmmword ptr [rax+10h], xmm0
0x100401fd4  mov     rbx, [rdi+8]
0x100401fd8  lea     rax, ??_7NamespaceSupport@@6B@; const NamespaceSupport::`vftable'
0x100401fdf  mov     [rdi+208h], rbx
0x100401fe6  mov     [rdi+200h], rax
0x100401fed  mov     [rdi+220h], rbx
0x100401ff4  lea     rax, ??_7?$_stack@UMap@NamespaceSupport@@$0BA@@@6B@; const _stack<NamespaceSupport::Map,16>::`vftable'
0x100401ffb  mov     [rdi+230h], ebp
0x100402001  lea     rcx, [rdi+238h]; void *
0x100402008  mov     [rdi+218h], rax
0x10040200f  xor     edx, edx; Val
0x100402011  mov     [rdi+228h], rcx
0x100402018  mov     r8d, 280h; Size
0x10040201e  mov     dword ptr [rdi+234h], 10h
0x100402028  call    memset
0x10040202d  mov     [rdi+4C0h], rbx
0x100402034  lea     rax, ??_7?$_dict@I$0A@@@6B@; const _dict<uint,0>::`vftable'
0x10040203b  mov     [rdi+4B8h], rax
0x100402042  lea     rax, ??_7DeclExternalId@@6B@; const DeclExternalId::`vftable'
0x100402049  mov     [rdi+4C8h], rbp
0x100402050  mov     [rdi+4D4h], ebp
0x100402056  mov     rdx, [rdi+8]
0x10040205a  mov     [rdi+4E8h], rax
0x100402061  mov     [rdi+4F0h], rdx
0x100402068  mov     [rdi+4F8h], rbp
0x10040206f  mov     [rdi+500h], ebp
0x100402075  mov     rax, cs:?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x10040207c  mov     ecx, cs:dword_100450B38
0x100402082  mov     [rdi+508h], rax
0x100402089  mov     [rdi+510h], ecx
0x10040208f  mov     rax, cs:?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x100402096  mov     ecx, cs:dword_100450B38
0x10040209c  mov     [rdi+518h], rax
0x1004020a3  mov     [rdi+520h], ecx
0x1004020a9  mov     rax, cs:?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x1004020b0  mov     ecx, cs:dword_100450B38
0x1004020b6  mov     [rdi+528h], rax
0x1004020bd  lea     rax, ??_7DeclDoctype@@6B@; const DeclDoctype::`vftable'
0x1004020c4  mov     [rdi+4E8h], rax
0x1004020cb  lea     rax, ??_7?$_htable@VDeclNotation@@@@6B@; const _htable<DeclNotation>::`vftable'
0x1004020d2  mov     [rdi+538h], rax
0x1004020d9  mov     [rdi+560h], rax
0x1004020e0  lea     rax, ??_7?$_htable@VDeclNotation@@@@6B@; const _htable<DeclNotation>::`vftable'
0x1004020e7  mov     [rdi+588h], rax
0x1004020ee  lea     rax, ??_7?$_htable@VDeclNotation@@@@6B@; const _htable<DeclNotation>::`vftable'
0x1004020f5  mov     [rdi+5B0h], rax
0x1004020fc  lea     rax, ?ParseError@YReader@@AEAAXXZ; YReader::ParseError(void)
0x100402103  mov     [rdi+530h], ecx
0x100402109  mov     [rdi+540h], rdx
0x100402110  mov     [rdi+548h], rbp
0x100402117  mov     [rdi+550h], ebp
0x10040211d  mov     [rdi+568h], rdx
0x100402124  mov     [rdi+570h], rbp
0x10040212b  mov     [rdi+578h], ebp
0x100402131  mov     [rdi+590h], rdx
0x100402138  mov     [rdi+598h], rbp
0x10040213f  mov     [rdi+5A0h], ebp
0x100402145  mov     [rdi+5B8h], rdx
0x10040214c  mov     [rdi+5C0h], rbp
0x100402153  mov     [rdi+5C8h], ebp
0x100402159  mov     [rdi+5D8h], rbp
0x100402160  mov     qword ptr [rsp+38h+var_18], rax
0x100402165  lea     rax, ?ParseElementN@YReader@@AEAAXXZ; YReader::ParseElementN(void)
0x10040216c  mov     dword ptr [rsp+38h+var_18+8], ebp
0x100402170  movups  xmm0, [rsp+38h+var_18]
0x100402175  mov     qword ptr [rsp+38h+var_18], rax
0x10040217a  lea     rax, ?ParseAttributesN@YReader@@AEAAXXZ; YReader::ParseAttributesN(void)
0x100402181  mov     dword ptr [rsp+38h+var_18+8], ebp
0x100402185  movups  xmmword ptr [rdi+5E0h], xmm0
0x10040218c  movups  xmm0, [rsp+38h+var_18]
0x100402191  mov     qword ptr [rsp+38h+var_18], rax
0x100402196  mov     dword ptr [rsp+38h+var_18+8], ebp
0x10040219a  movups  xmmword ptr [rdi+600h], xmm0
0x1004021a1  movups  xmm0, [rsp+38h+var_18]
0x1004021a6  movups  xmmword ptr [rdi+610h], xmm0
0x1004021ad  mov     [rdi+620h], rbp
0x1004021b4  mov     [rdi+628h], ebp
0x1004021ba  mov     [rdi+630h], rbp
0x1004021c1  mov     [rdi+638h], ebp
0x1004021c7  mov     [rdi+640h], rbp
0x1004021ce  mov     [rdi+648h], ebp
0x1004021d4  mov     [rdi+650h], rbp
0x1004021db  mov     [rdi+658h], ebp
0x1004021e1  mov     [rdi+660h], rbp
0x1004021e8  mov     [rdi+668h], ebp
0x1004021ee  mov     [rdi+670h], rbp
0x1004021f5  mov     [rdi+678h], ebp
0x1004021fb  mov     [rdi+680h], rbp
0x100402202  xor     edx, edx; Val
0x100402204  mov     [rdi+688h], ebp
0x10040220a  mov     r8d, 380h; Size
0x100402210  mov     [rdi+690h], rbp
0x100402217  mov     [rdi+698h], ebp
0x10040221d  mov     [rdi+6A0h], rbp
0x100402224  mov     [rdi+6A8h], ebp
0x10040222a  mov     ecx, cs:dword_100450B38
0x100402230  mov     rax, cs:?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x100402237  mov     [rdi+6B0h], rax
0x10040223e  mov     [rdi+6B8h], ecx
0x100402244  mov     ecx, cs:dword_100450B38
0x10040224a  mov     rax, cs:?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x100402251  mov     [rdi+6C0h], rax
0x100402258  mov     [rdi+6C8h], ecx
0x10040225e  mov     ecx, cs:dword_100450B38
0x100402264  mov     rax, cs:?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x10040226b  mov     [rdi+6D0h], rax
0x100402272  mov     [rdi+6D8h], ecx
0x100402278  mov     rax, cs:?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x10040227f  mov     ecx, cs:dword_100450B38
0x100402285  mov     [rdi+6E0h], rax
0x10040228c  mov     [rdi+6E8h], ecx
0x100402292  lea     rcx, [rdi+768h]; void *
0x100402299  mov     rax, [rdi+8]
0x10040229d  mov     [rdi+750h], rax
0x1004022a4  lea     rax, ??_7?$_stack@UElement@YReader@@$0BA@@@6B@; const _stack<YReader::Element,16>::`vftable'
0x1004022ab  mov     [rdi+748h], rax
0x1004022b2  mov     [rdi+6F0h], ebp
0x1004022b8  mov     qword ptr [rdi+6F4h], 1
0x1004022c3  mov     [rdi+6FCh], rbp
0x1004022ca  mov     byte ptr [rdi+704h], 1
0x1004022d1  mov     [rdi+728h], rbp
0x1004022d8  mov     [rdi+730h], rbp
0x1004022df  mov     [rdi+740h], ebp
0x1004022e5  mov     [rdi+758h], rcx
0x1004022ec  mov     [rdi+760h], ebp
0x1004022f2  mov     dword ptr [rdi+764h], 10h
0x1004022fc  call    memset
0x100402301  mov     rax, [rdi+8]
0x100402305  lea     rcx, [rdi+0B20h]; void *
0x10040230c  lea     rbx, ??_7?$_stack@UAttribute@@$0BA@@@6B@; const _stack<Attribute,16>::`vftable'
0x100402313  mov     [rdi+0B08h], rax
0x10040231a  xor     edx, edx; Val
0x10040231c  mov     [rdi+0B10h], rcx
0x100402323  mov     r8d, 980h; Size
0x100402329  mov     [rdi+0AE8h], rbp
0x100402330  mov     [rdi+0AF0h], rbp
0x100402337  mov     [rdi+0B00h], rbx
0x10040233e  mov     [rdi+0B18h], ebp
0x100402344  mov     dword ptr [rdi+0B1Ch], 10h
0x10040234e  call    memset
0x100402353  mov     rax, [rdi+8]
0x100402357  lea     rcx, [rdi+14C0h]; void *
0x10040235e  xor     edx, edx; Val
0x100402360  mov     [rdi+14A8h], rax
0x100402367  mov     r8d, 980h; Size
0x10040236d  mov     [rdi+14B0h], rcx
0x100402374  mov     [rdi+14A0h], rbx
0x10040237b  mov     [rdi+14B8h], ebp
0x100402381  mov     dword ptr [rdi+14BCh], 10h
0x10040238b  call    memset
0x100402390  mov     rax, [rdi+8]
0x100402394  lea     rcx, [rdi+1E60h]; void *
0x10040239b  mov     [rdi+1E48h], rax
0x1004023a2  xor     edx, edx; Val
0x1004023a4  lea     rax, ??_7?$_stack@UAttValueToken@@$0BA@@@6B@; const _stack<AttValueToken,16>::`vftable'
0x1004023ab  mov     [rdi+1E50h], rcx
0x1004023b2  mov     r8d, 180h; Size
0x1004023b8  mov     [rdi+1E40h], rax
0x1004023bf  mov     [rdi+1E58h], ebp
0x1004023c5  mov     dword ptr [rdi+1E5Ch], 10h
0x1004023cf  call    memset
0x1004023d4  mov     rax, [rdi+8]
0x1004023d8  mov     [rdi+1FE8h], rax
0x1004023df  lea     rax, ??_7?$_stack@I$0BA@@@6B@; const _stack<uint,16>::`vftable'
0x1004023e6  mov     [rdi+1FE0h], rax
0x1004023ed  lea     rax, [rdi+2000h]
0x1004023f4  mov     [rdi+1FF0h], rax
0x1004023fb  mov     [rdi+1FF8h], ebp
0x100402401  mov     dword ptr [rdi+1FFCh], 10h
0x10040240b  xorps   xmm0, xmm0
0x10040240e  movups  xmmword ptr [rax], xmm0
0x100402411  movups  xmmword ptr [rax+10h], xmm0
0x100402415  movups  xmmword ptr [rax+20h], xmm0
0x100402419  movups  xmmword ptr [rax+30h], xmm0
0x10040241d  mov     [rdi+2040h], rbp
0x100402424  mov     dword ptr [rdi+204Ch], 1
0x10040242e  test    rsi, rsi
0x100402431  jz      short loc_100402443
0x100402433  mov     rax, [rsi]
0x100402436  mov     rcx, rsi
0x100402439  mov     rax, [rax+8]
0x10040243d  call    cs:__guard_dispatch_icall_fptr
0x100402443  call    cs:__imp_GetTickCount
0x100402449  mov     ecx, eax
0x10040244b  shl     ecx, 7
0x10040244e  xor     ecx, eax
0x100402450  shl     ecx, 0Bh
0x100402453  xor     ecx, eax
0x100402455  mov     [rdi+0AF8h], ecx
0x10040245b  lea     rcx, ?s_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x100402462  call    cs:__imp_EnterCriticalSection
0x100402468  inc     cs:?s_cComponents@@3JA; long s_cComponents
0x10040246e  lea     rcx, ?s_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x100402475  call    cs:__imp_LeaveCriticalSection
0x10040247b  mov     rbx, [rsp+38h+arg_0]
0x100402480  mov     rax, rdi
0x100402483  mov     rbp, [rsp+38h+arg_8]
0x100402488  mov     rsi, [rsp+38h+arg_10]
0x10040248d  add     rsp, 30h
0x100402491  pop     rdi
0x100402492  retn
```
