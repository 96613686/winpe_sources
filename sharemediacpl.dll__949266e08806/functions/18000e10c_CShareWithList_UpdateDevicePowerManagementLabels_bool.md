# CShareWithList::UpdateDevicePowerManagementLabels(bool)

- ea: `0x18000e10c`
- end: `0x18000e1ed`
- name: `?UpdateDevicePowerManagementLabels@CShareWithList@@QEAAJ_N@Z`
- size: `225`
- prototype: `__int64 __fastcall(CShareWithList *__hidden this, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180010bec`

## callees

- `0x180003860`
- `0x180003888`
- `0x18000db20`
- `0x18000e10c`
- `0x18000e1f4`
- `0x180016460`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000e1ae`
- `KERNEL32!LeaveCriticalSection` at `0x18000e1ae`
- `KERNEL32!EnterCriticalSection` at `0x18000e150`
- `KERNEL32!EnterCriticalSection` at `0x18000e150`

## pseudocode

```c
__int64 __fastcall CShareWithList::UpdateDevicePowerManagementLabels(CShareWithList *this, char a2)
{
  bool v4; // zf
  unsigned int v5; // ebx
  int i; // esi
  struct _DPA *v7; // rcx
  int v8; // eax
  CShareWithListItemBase *Ptr; // rax
  CShareWithListItemBase *v10; // rbp

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v4 = *((_QWORD *)this + 3) == 0;
  *((_BYTE *)this + 112) = a2;
  if ( v4 )
  {
    v5 = -2147024809;
  }
  else
  {
    v5 = 0;
    for ( i = 0; ; ++i )
    {
      v7 = (struct _DPA *)*((_QWORD *)this + 3);
      v8 = v7 ? *(_DWORD *)v7 : 0;
      if ( i >= v8 )
        break;
      Ptr = (CShareWithListItemBase *)DPA_GetPtr(v7, i);
      v10 = Ptr;
      if ( Ptr )
      {
        CShareWithListItemBase::SetShowPowerManagementLabel(Ptr, *((_BYTE *)this + 112) == 0);
        CShareWithListItemBase::UpdateUI(v10, 0);
      }
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18000e10c  push    rbx
0x18000e10e  push    rbp
0x18000e10f  push    rsi
0x18000e110  push    rdi
0x18000e111  push    r14
0x18000e113  push    r15
0x18000e115  sub     rsp, 28h
0x18000e119  mov     bl, dl
0x18000e11b  mov     rdi, rcx
0x18000e11e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e125  lea     r15, WPP_GLOBAL_Control
0x18000e12c  cmp     rcx, r15
0x18000e12f  jz      short loc_18000E14C
0x18000e131  test    byte ptr [rcx+1Ch], 20h
0x18000e135  jz      short loc_18000E14C
0x18000e137  mov     rcx, [rcx+10h]
0x18000e13b  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000e142  mov     edx, 7Eh ; '~'
0x18000e147  call    WPP_SF_
0x18000e14c  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000e150  call    cs:__imp_EnterCriticalSection
0x18000e156  cmp     qword ptr [rdi+18h], 0
0x18000e15b  mov     [rdi+70h], bl
0x18000e15e  jz      short loc_18000E1A5
0x18000e160  xor     ebx, ebx
0x18000e162  xor     esi, esi
0x18000e164  mov     rcx, [rdi+18h]; hdpa
0x18000e168  test    rcx, rcx
0x18000e16b  jz      short loc_18000E171
0x18000e16d  mov     eax, [rcx]
0x18000e16f  jmp     short loc_18000E173
0x18000e171  xor     eax, eax
0x18000e173  cmp     esi, eax
0x18000e175  jge     short loc_18000E1AA
0x18000e177  movsxd  rdx, esi; i
0x18000e17a  call    DPA_GetPtr
0x18000e17f  mov     rbp, rax
0x18000e182  test    rax, rax
0x18000e185  jz      short loc_18000E1A1
0x18000e187  xor     edx, edx
0x18000e189  mov     rcx, rax; this
0x18000e18c  cmp     [rdi+70h], dl
0x18000e18f  setz    dl; int
0x18000e192  call    ?SetShowPowerManagementLabel@CShareWithListItemBase@@QEAAJH@Z; CShareWithListItemBase::SetShowPowerManagementLabel(int)
0x18000e197  xor     edx, edx; int
0x18000e199  mov     rcx, rbp; this
0x18000e19c  call    ?UpdateUI@CShareWithListItemBase@@QEAAJH@Z; CShareWithListItemBase::UpdateUI(int)
0x18000e1a1  inc     esi
0x18000e1a3  jmp     short loc_18000E164
0x18000e1a5  mov     ebx, 80070057h
0x18000e1aa  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000e1ae  call    cs:__imp_LeaveCriticalSection
0x18000e1b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1bb  cmp     rcx, r15
0x18000e1be  jz      short loc_18000E1DE
0x18000e1c0  test    byte ptr [rcx+1Ch], 20h
0x18000e1c4  jz      short loc_18000E1DE
0x18000e1c6  mov     rcx, [rcx+10h]
0x18000e1ca  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000e1d1  mov     edx, 7Fh
0x18000e1d6  mov     r9d, ebx
0x18000e1d9  call    WPP_SF_d
0x18000e1de  mov     eax, ebx
0x18000e1e0  add     rsp, 28h
0x18000e1e4  pop     r15
0x18000e1e6  pop     r14
0x18000e1e8  pop     rdi
0x18000e1e9  pop     rsi
0x18000e1ea  pop     rbp
0x18000e1eb  pop     rbx
0x18000e1ec  retn
```
