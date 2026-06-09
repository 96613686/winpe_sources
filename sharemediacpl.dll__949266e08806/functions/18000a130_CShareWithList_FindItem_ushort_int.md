# CShareWithList::FindItem(ushort *,int *)

- ea: `0x18000a130`
- end: `0x18000a3cd`
- name: `?FindItem@CShareWithList@@QEAAJPEAGPEAH@Z`
- size: `669`
- prototype: `int(CShareWithList *__hidden this, unsigned __int16 *, int *)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18000822c`
- `0x1800087c0`
- `0x18000d338`
- `0x18000df2c`

## callees

- `0x180003860`
- `0x180003888`
- `0x180004c40`
- `0x18000a130`
- `0x18000a530`
- `0x180012dd8`
- `0x1800163c0`
- `0x180016460`
- `0x18001e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000a386`
- `KERNEL32!LeaveCriticalSection` at `0x18000a386`
- `KERNEL32!EnterCriticalSection` at `0x18000a17f`
- `KERNEL32!EnterCriticalSection` at `0x18000a17f`
- `KERNEL32!lstrcmpiW` at `0x18000a29d`
- `KERNEL32!lstrcmpiW` at `0x18000a29d`
- `ole32!CoTaskMemFree` at `0x18000a334`
- `ole32!CoTaskMemFree` at `0x18000a334`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000a327`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000a327`

## pseudocode

```c
__int64 __fastcall CShareWithList::FindItem(CShareWithList *this, unsigned __int16 *a2, int *a3)
{
  unsigned __int16 *v6; // rax
  __int64 v7; // r8
  int DeviceSettings; // ebx
  int i; // edi
  struct _DPA *v10; // rcx
  int v11; // eax
  CShareWithListItemBase *Ptr; // rax
  DirectUI::Element *v13; // rbp
  CDeviceSettings *v14; // r14
  _QWORD *v15; // rcx
  LPCWSTR lpString1; // [rsp+60h] [rbp+8h] BYREF
  CDeviceSettings *v18; // [rsp+68h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( !a2 )
    goto LABEL_42;
  v6 = a2;
  v7 = 0x7FFFFFFF;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v7;
  }
  while ( v7 );
  if ( (v7 != 0 ? 0x7FFFFFFF - (_DWORD)v7 : 0) != 0 && a3 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 124, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, a2);
    *a3 = -1;
    if ( *((_QWORD *)this + 3) )
    {
      DeviceSettings = 0;
      for ( i = 0; ; ++i )
      {
        v10 = (struct _DPA *)*((_QWORD *)this + 3);
        v11 = v10 ? *(_DWORD *)v10 : 0;
        if ( i >= v11 || DeviceSettings < 0 )
          break;
        if ( *a3 != -1 )
          goto LABEL_43;
        Ptr = (CShareWithListItemBase *)DPA_GetPtr(v10, i);
        v13 = Ptr;
        if ( Ptr )
        {
          v18 = 0;
          DeviceSettings = CShareWithListItemBase::GetDeviceSettings(Ptr, &v18);
          if ( DeviceSettings >= 0 )
          {
            lpString1 = 0;
            v14 = v18;
            DeviceSettings = CDeviceSettings::GetID(v18, (unsigned __int16 **)&lpString1);
            if ( DeviceSettings >= 0 )
            {
              if ( !lstrcmpiW(lpString1, a2) )
              {
                v15 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
                {
                  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
                    v15 = WPP_GLOBAL_Control;
                  }
                  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x20) != 0 )
                    WPP_SF_(v15[2], 39, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
                }
                if ( *((_DWORD *)v14 + 21) )
                {
                  DPA_DeletePtr(*((HDPA *)this + 3), i);
                  if ( (*((_BYTE *)v13 + 151) & 4) == 0 )
                    DirectUI::Element::Destroy(v13, 1);
                }
                *a3 = i;
              }
              CoTaskMemFree((LPVOID)lpString1);
            }
            (*(void (__fastcall **)(CDeviceSettings *))(*(_QWORD *)v14 + 16LL))(v14);
          }
        }
        else
        {
          DeviceSettings = -2147467259;
        }
      }
      if ( *a3 == -1 )
        DeviceSettings = 1;
    }
    else
    {
      DeviceSettings = -2147024809;
    }
  }
  else
  {
LABEL_42:
    DeviceSettings = -2147467261;
  }
LABEL_43:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      125,
      &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids,
      (unsigned int)DeviceSettings);
  return (unsigned int)DeviceSettings;
}

```

## disassembly

```asm
0x18000a130  mov     [rsp+arg_10], rbx
0x18000a135  push    rbp
0x18000a136  push    rsi
0x18000a137  push    rdi
0x18000a138  push    r12
0x18000a13a  push    r13
0x18000a13c  push    r14
0x18000a13e  push    r15
0x18000a140  sub     rsp, 20h
0x18000a144  mov     rsi, r8
0x18000a147  mov     r12, rdx
0x18000a14a  mov     r15, rcx
0x18000a14d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a154  lea     rbp, WPP_GLOBAL_Control
0x18000a15b  cmp     rcx, rbp
0x18000a15e  jz      short loc_18000A17B
0x18000a160  test    byte ptr [rcx+1Ch], 20h
0x18000a164  jz      short loc_18000A17B
0x18000a166  mov     rcx, [rcx+10h]
0x18000a16a  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000a171  mov     edx, 7Bh ; '{'
0x18000a176  call    WPP_SF_
0x18000a17b  lea     rcx, [r15+48h]; lpCriticalSection
0x18000a17f  call    cs:__imp_EnterCriticalSection
0x18000a185  xor     r14d, r14d
0x18000a188  test    r12, r12
0x18000a18b  jz      loc_18000A374
0x18000a191  mov     r9d, 7FFFFFFFh
0x18000a197  mov     rax, r12
0x18000a19a  mov     r8d, r9d
0x18000a19d  cmp     [rax], r14w
0x18000a1a1  jz      short loc_18000A1AD
0x18000a1a3  add     rax, 2
0x18000a1a7  sub     r8, 1
0x18000a1ab  jnz     short loc_18000A19D
0x18000a1ad  sub     r9d, r8d
0x18000a1b0  mov     rax, r8
0x18000a1b3  neg     rax
0x18000a1b6  mov     rdx, r8
0x18000a1b9  sbb     ecx, ecx
0x18000a1bb  and     ecx, r9d
0x18000a1be  neg     rdx
0x18000a1c1  sbb     edx, edx
0x18000a1c3  and     edx, ecx
0x18000a1c5  neg     r8
0x18000a1c8  sbb     eax, eax
0x18000a1ca  test    edx, eax
0x18000a1cc  jbe     loc_18000A374
0x18000a1d2  test    rsi, rsi
0x18000a1d5  jz      loc_18000A374
0x18000a1db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1e2  cmp     rcx, rbp
0x18000a1e5  jz      short loc_18000A205
0x18000a1e7  test    byte ptr [rcx+1Ch], 8
0x18000a1eb  jz      short loc_18000A205
0x18000a1ed  mov     rcx, [rcx+10h]
0x18000a1f1  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000a1f8  mov     edx, 7Ch ; '|'
0x18000a1fd  mov     r9, r12
0x18000a200  call    WPP_SF_S
0x18000a205  mov     dword ptr [rsi], 0FFFFFFFFh
0x18000a20b  cmp     [r15+18h], r14
0x18000a20f  jz      loc_18000A36D
0x18000a215  mov     ebx, r14d
0x18000a218  mov     edi, r14d
0x18000a21b  mov     rcx, [r15+18h]; hdpa
0x18000a21f  test    rcx, rcx
0x18000a222  jz      short loc_18000A228
0x18000a224  mov     eax, [rcx]
0x18000a226  jmp     short loc_18000A22B
0x18000a228  mov     eax, r14d
0x18000a22b  cmp     edi, eax
0x18000a22d  jge     loc_18000A35A
0x18000a233  test    ebx, ebx
0x18000a235  js      loc_18000A35A
0x18000a23b  cmp     dword ptr [rsi], 0FFFFFFFFh
0x18000a23e  jnz     loc_18000A37B
0x18000a244  movsxd  rdx, edi; i
0x18000a247  call    DPA_GetPtr
0x18000a24c  mov     rbp, rax
0x18000a24f  test    rax, rax
0x18000a252  jz      loc_18000A34E
0x18000a258  lea     rdx, [rsp+58h+arg_8]; struct CDeviceSettings **
0x18000a25d  mov     [rsp+58h+arg_8], r14
0x18000a262  mov     rcx, rax; this
0x18000a265  call    ?GetDeviceSettings@CShareWithListItemBase@@QEAAJPEAPEAVCDeviceSettings@@@Z; CShareWithListItemBase::GetDeviceSettings(CDeviceSettings * *)
0x18000a26a  mov     ebx, eax
0x18000a26c  test    eax, eax
0x18000a26e  js      loc_18000A353
0x18000a274  mov     [rsp+58h+lpString1], r14
0x18000a279  lea     rdx, [rsp+58h+lpString1]; unsigned __int16 **
0x18000a27e  mov     r14, [rsp+58h+arg_8]
0x18000a283  mov     rcx, r14; this
0x18000a286  call    ?GetID@CDeviceSettings@@QEAAJPEAPEAG@Z; CDeviceSettings::GetID(ushort * *)
0x18000a28b  mov     ebx, eax
0x18000a28d  test    eax, eax
0x18000a28f  js      loc_18000A33A
0x18000a295  mov     rcx, [rsp+58h+lpString1]; lpString1
0x18000a29a  mov     rdx, r12; lpString2
0x18000a29d  call    cs:__imp_lstrcmpiW
0x18000a2a3  test    eax, eax
0x18000a2a5  jnz     loc_18000A32F
0x18000a2ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2b2  lea     rax, WPP_GLOBAL_Control
0x18000a2b9  cmp     rcx, rax
0x18000a2bc  jz      short loc_18000A307
0x18000a2be  test    byte ptr [rcx+1Ch], 20h
0x18000a2c2  jz      short loc_18000A2E7
0x18000a2c4  mov     rcx, [rcx+10h]
0x18000a2c8  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x18000a2cf  mov     edx, 26h ; '&'
0x18000a2d4  call    WPP_SF_
0x18000a2d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2e0  lea     rax, WPP_GLOBAL_Control
0x18000a2e7  cmp     rcx, rax
0x18000a2ea  jz      short loc_18000A307
0x18000a2ec  test    byte ptr [rcx+1Ch], 20h
0x18000a2f0  jz      short loc_18000A307
0x18000a2f2  mov     rcx, [rcx+10h]
0x18000a2f6  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x18000a2fd  mov     edx, 27h ; '''
0x18000a302  call    WPP_SF_
0x18000a307  cmp     dword ptr [r14+54h], 0
0x18000a30c  jz      short loc_18000A32D
0x18000a30e  mov     rcx, [r15+18h]; hdpa
0x18000a312  mov     edx, edi; i
0x18000a314  call    DPA_DeletePtr
0x18000a319  test    byte ptr [rbp+97h], 4
0x18000a320  jnz     short loc_18000A32D
0x18000a322  mov     dl, 1
0x18000a324  mov     rcx, rbp
0x18000a327  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18000a32d  mov     [rsi], edi
0x18000a32f  mov     rcx, [rsp+58h+lpString1]; pv
0x18000a334  call    cs:__imp_CoTaskMemFree
0x18000a33a  mov     rax, [r14]
0x18000a33d  mov     rcx, r14
0x18000a340  mov     rax, [rax+10h]
0x18000a344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a349  xor     r14d, r14d
0x18000a34c  jmp     short loc_18000A353
0x18000a34e  mov     ebx, 80004005h
0x18000a353  inc     edi
0x18000a355  jmp     loc_18000A21B
0x18000a35a  cmp     dword ptr [rsi], 0FFFFFFFFh
0x18000a35d  lea     rbp, WPP_GLOBAL_Control
0x18000a364  jnz     short loc_18000A382
0x18000a366  mov     ebx, 1
0x18000a36b  jmp     short loc_18000A382
0x18000a36d  mov     ebx, 80070057h
0x18000a372  jmp     short loc_18000A382
0x18000a374  mov     ebx, 80004003h
0x18000a379  jmp     short loc_18000A382
0x18000a37b  lea     rbp, WPP_GLOBAL_Control
0x18000a382  lea     rcx, [r15+48h]; lpCriticalSection
0x18000a386  call    cs:__imp_LeaveCriticalSection
0x18000a38c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a393  cmp     rcx, rbp
0x18000a396  jz      short loc_18000A3B6
0x18000a398  test    byte ptr [rcx+1Ch], 20h
0x18000a39c  jz      short loc_18000A3B6
0x18000a39e  mov     rcx, [rcx+10h]
0x18000a3a2  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000a3a9  mov     edx, 7Dh ; '}'
0x18000a3ae  mov     r9d, ebx
0x18000a3b1  call    WPP_SF_d
0x18000a3b6  mov     eax, ebx
0x18000a3b8  mov     rbx, [rsp+58h+arg_10]
0x18000a3bd  add     rsp, 20h
0x18000a3c1  pop     r15
0x18000a3c3  pop     r14
0x18000a3c5  pop     r13
0x18000a3c7  pop     r12
0x18000a3c9  pop     rdi
0x18000a3ca  pop     rsi
0x18000a3cb  pop     rbp
0x18000a3cc  retn
```
