# CSamPropStore::SetValue(_tagpropertykey const &,tagPROPVARIANT const &)

- ea: `0x180015570`
- end: `0x180015659`
- name: `?SetValue@CSamPropStore@@UEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z`
- size: `233`
- prototype: `__int64 __fastcall(CSamPropStore *__hidden this, const struct _tagpropertykey *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180006f80`
- `0x180015570`
- `0x1800166f4`
- `0x18001675c`
- `0x180017010`

## import_xrefs

- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800155e7`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x1800155e7`

## pseudocode

```c
__int64 __fastcall CSamPropStore::SetValue(
        CSamPropStore *this,
        const struct _tagpropertykey *a2,
        const struct tagPROPVARIANT *a3)
{
  HRESULT v6; // edi
  __int64 v7; // r8

  v6 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF__guid_ddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      a3,
      a2,
      a2->pid,
      *((_DWORD *)this + 20),
      *((_DWORD *)this + 21));
  if ( !(unsigned int)CSamPropStore::_FindSamPropKey(this, a2, 0) )
  {
    if ( !*((_QWORD *)this + 12)
      && (v6 = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, (void **)this + 12), v6 < 0)
      || (v6 = (*(__int64 (__fastcall **)(_QWORD, const struct _tagpropertykey *, const struct tagPROPVARIANT *))(**((_QWORD **)this + 12) + 48LL))(
                 *((_QWORD *)this + 12),
                 a2,
                 a3),
          v6 < 0) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF__guid_dddD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          v7,
          a2,
          a2->pid,
          *((_DWORD *)this + 20),
          *((_DWORD *)this + 21),
          v6);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180015570  push    rbx
0x180015572  push    rbp
0x180015573  push    rsi
0x180015574  push    rdi
0x180015575  push    r14
0x180015577  push    r15
0x180015579  sub     rsp, 48h
0x18001557d  mov     rbp, r8
0x180015580  mov     rsi, rdx
0x180015583  mov     rbx, rcx
0x180015586  xor     edi, edi
0x180015588  mov     rcx, cs:WPP_GLOBAL_Control
0x18001558f  lea     r15, WPP_GLOBAL_Control
0x180015596  cmp     rcx, r15
0x180015599  jz      short loc_1800155C2
0x18001559b  test    byte ptr [rcx+1Ch], 8
0x18001559f  jz      short loc_1800155C2
0x1800155a1  mov     eax, [rbx+54h]
0x1800155a4  mov     r9, rdx
0x1800155a7  mov     rcx, [rcx+10h]
0x1800155ab  mov     [rsp+78h+var_48], eax
0x1800155af  mov     eax, [rbx+50h]
0x1800155b2  mov     [rsp+78h+var_50], eax
0x1800155b6  mov     eax, [rdx+10h]
0x1800155b9  mov     [rsp+78h+var_58], eax
0x1800155bd  call    WPP_SF__guid_ddd
0x1800155c2  xor     r8d, r8d; struct _PROPMAP **
0x1800155c5  mov     rdx, rsi; struct _tagpropertykey *
0x1800155c8  mov     rcx, rbx; this
0x1800155cb  call    ?_FindSamPropKey@CSamPropStore@@AEAAJAEBU_tagpropertykey@@PEAPEAU_PROPMAP@@@Z; CSamPropStore::_FindSamPropKey(_tagpropertykey const &,_PROPMAP * *)
0x1800155d0  test    eax, eax
0x1800155d2  jnz     short loc_18001564A
0x1800155d4  lea     r14, [rbx+60h]
0x1800155d8  cmp     [r14], rdi
0x1800155db  jnz     short loc_1800155F3
0x1800155dd  mov     rdx, r14; ppv
0x1800155e0  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x1800155e7  call    cs:__imp_PSCreateMemoryPropertyStore
0x1800155ed  mov     edi, eax
0x1800155ef  test    eax, eax
0x1800155f1  js      short loc_18001560E
0x1800155f3  mov     rcx, [r14]
0x1800155f6  mov     r8, rbp
0x1800155f9  mov     rdx, rsi
0x1800155fc  mov     rax, [rcx]
0x1800155ff  mov     rax, [rax+30h]
0x180015603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015608  mov     edi, eax
0x18001560a  test    eax, eax
0x18001560c  jns     short loc_18001564A
0x18001560e  mov     rcx, cs:WPP_GLOBAL_Control
0x180015615  cmp     rcx, r15
0x180015618  jz      short loc_18001564A
0x18001561a  test    byte ptr [rcx+1Ch], 4
0x18001561e  jz      short loc_18001564A
0x180015620  mov     eax, [rbx+54h]
0x180015623  mov     edx, 0Bh
0x180015628  mov     rcx, [rcx+10h]
0x18001562c  mov     r9, rsi
0x18001562f  mov     [rsp+78h+var_40], edi
0x180015633  mov     [rsp+78h+var_48], eax
0x180015637  mov     eax, [rbx+50h]
0x18001563a  mov     [rsp+78h+var_50], eax
0x18001563e  mov     eax, [rsi+10h]
0x180015641  mov     [rsp+78h+var_58], eax
0x180015645  call    WPP_SF__guid_dddD
0x18001564a  mov     eax, edi
0x18001564c  add     rsp, 48h
0x180015650  pop     r15
0x180015652  pop     r14
0x180015654  pop     rdi
0x180015655  pop     rsi
0x180015656  pop     rbp
0x180015657  pop     rbx
0x180015658  retn
```
