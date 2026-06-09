# CWdsMetadataFactory::CreateInstance(ATL::CComObject<CWdsMetadataFactory> * *)

- ea: `0x180007798`
- end: `0x18000789f`
- name: `?CreateInstance@CWdsMetadataFactory@@SAJPEAPEAV?$CComObject@VCWdsMetadataFactory@@@ATL@@@Z`
- size: `263`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003acc`

## callees

- `0x180001cd0`
- `0x180007798`
- `0x180014ee0`
- `0x180015068`
- `0x180015c9d`
- `0x180015cc0`

## pseudocode

```c
__int64 __fastcall CWdsMetadataFactory::CreateInstance(_QWORD *a1)
{
  unsigned int v2; // esi
  char *v3; // rax
  const char *v4; // rdx
  _BYTE *v5; // rdi
  int v6; // eax
  _BYTE *v7; // rbx

  v2 = -2147024882;
  v3 = (char *)operator new(0x40u);
  v5 = v3;
  if ( v3 )
  {
    *((_DWORD *)v3 + 2) = 0;
    memset_0(v3 + 16, 0, 0x28u);
    v5[56] = 0;
    *(_QWORD *)v5 = &ATL::CComObject<CWdsMetadataFactory>::`vftable';
    _InterlockedIncrement((volatile signed __int32 *)ATL::_pAtlModule + 3);
  }
  else
  {
    v5 = 0;
  }
  if ( v5 )
  {
    v6 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v5 + 16));
    if ( v6 >= 0 )
    {
      v5[56] = 1;
      v6 = 0;
    }
    v2 = 0;
    if ( v6 < 0 )
      v2 = v6;
    if ( v2 )
    {
      (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v5 + 40LL))(v5, 1);
      v5 = 0;
    }
  }
  v7 = v5;
  if ( (int)ElValidateHr(v2, v4, "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\wdsmetadatafactory.cpp", 0x5Eu) >= 0 )
  {
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v5 + 8LL))(v5);
    *a1 = v5;
    v7 = 0;
    v5 = 0;
  }
  if ( v7 )
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v5 + 16LL))(v5);
  return v2;
}

```

## disassembly

```asm
0x180007798  mov     rax, rsp
0x18000779b  mov     [rax+8], rbx
0x18000779f  mov     [rax+10h], rbp
0x1800077a3  mov     [rax+18h], rsi
0x1800077a7  mov     [rax+20h], rdi
0x1800077ab  push    r14
0x1800077ad  sub     rsp, 20h
0x1800077b1  mov     r14, rcx
0x1800077b4  mov     esi, 8007000Eh
0x1800077b9  mov     ecx, 40h ; '@'; Size
0x1800077be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800077c3  xor     ebp, ebp
0x1800077c5  mov     rdi, rax
0x1800077c8  test    rax, rax
0x1800077cb  jz      short loc_1800077FA
0x1800077cd  xor     edx, edx; Val
0x1800077cf  mov     [rax+8], ebp
0x1800077d2  lea     r8d, [rbp+28h]; Size
0x1800077d6  lea     rcx, [rax+10h]; void *
0x1800077da  call    memset_0
0x1800077df  lea     rax, ??_7?$CComObject@VCWdsMetadataFactory@@@ATL@@6B@; const ATL::CComObject<CWdsMetadataFactory>::`vftable'
0x1800077e6  mov     [rdi+38h], bpl
0x1800077ea  mov     [rdi], rax
0x1800077ed  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800077f4  lock inc dword ptr [rax+0Ch]
0x1800077f8  jmp     short loc_1800077FD
0x1800077fa  mov     rdi, rbp
0x1800077fd  test    rdi, rdi
0x180007800  jz      short loc_180007839
0x180007802  lea     rcx, [rdi+10h]; this
0x180007806  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000780b  test    eax, eax
0x18000780d  js      short loc_180007813
0x18000780f  mov     byte ptr [rdi+38h], 1
0x180007813  cmovns  eax, ebp
0x180007816  mov     esi, ebp
0x180007818  test    eax, eax
0x18000781a  cmovs   esi, eax
0x18000781d  test    esi, esi
0x18000781f  jz      short loc_180007839
0x180007821  mov     rax, [rdi]
0x180007824  mov     edx, 1
0x180007829  mov     rcx, rdi
0x18000782c  mov     rax, [rax+28h]
0x180007830  call    cs:__guard_dispatch_icall_fptr
0x180007836  mov     rdi, rbp
0x180007839  mov     r9d, 5Eh ; '^'; unsigned int
0x18000783f  lea     r8, aBaseEcoWdsWdss; "base\\eco\\wds\\wdssrv\\wdsdcmgr\\src\\"...
0x180007846  mov     ecx, esi; int
0x180007848  mov     rbx, rdi
0x18000784b  call    ?ElValidateHr@@YAJJPEBD0K@Z; ElValidateHr(long,char const *,char const *,ulong)
0x180007850  test    eax, eax
0x180007852  js      short loc_18000786D
0x180007854  mov     rax, [rdi]
0x180007857  mov     rcx, rdi
0x18000785a  mov     rax, [rax+8]
0x18000785e  call    cs:__guard_dispatch_icall_fptr
0x180007864  mov     [r14], rdi
0x180007867  mov     rbx, rbp
0x18000786a  mov     rdi, rbp
0x18000786d  test    rbx, rbx
0x180007870  jz      short loc_180007882
0x180007872  mov     rdx, [rdi]
0x180007875  mov     rcx, rdi
0x180007878  mov     rax, [rdx+10h]
0x18000787c  call    cs:__guard_dispatch_icall_fptr
0x180007882  mov     rbx, [rsp+28h+arg_0]
0x180007887  mov     eax, esi
0x180007889  mov     rsi, [rsp+28h+arg_10]
0x18000788e  mov     rbp, [rsp+28h+arg_8]
0x180007893  mov     rdi, [rsp+28h+arg_18]
0x180007898  add     rsp, 20h
0x18000789c  pop     r14
0x18000789e  retn
```
