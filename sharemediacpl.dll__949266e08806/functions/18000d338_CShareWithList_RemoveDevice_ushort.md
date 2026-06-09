# CShareWithList::RemoveDevice(ushort *)

- ea: `0x18000d338`
- end: `0x18000d50e`
- name: `?RemoveDevice@CShareWithList@@QEAAJPEAG@Z`
- size: `470`
- prototype: `__int64 __fastcall(CShareWithList *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180009900`

## callees

- `0x180003860`
- `0x180003888`
- `0x18000a130`
- `0x18000d338`
- `0x180012cb0`
- `0x180012dd8`
- `0x1800163c0`
- `0x180016460`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000d44b`
- `KERNEL32!LeaveCriticalSection` at `0x18000d48a`
- `KERNEL32!LeaveCriticalSection` at `0x18000d44b`
- `KERNEL32!LeaveCriticalSection` at `0x18000d48a`
- `KERNEL32!EnterCriticalSection` at `0x18000d424`
- `KERNEL32!EnterCriticalSection` at `0x18000d424`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000d4a2`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x18000d4a2`

## pseudocode

```c
__int64 __fastcall CShareWithList::RemoveDevice(CShareWithList *this, unsigned __int16 *a2)
{
  CShareWithList *v3; // r14
  _QWORD *v4; // r10
  unsigned __int16 *v5; // rax
  __int64 v6; // r8
  unsigned int Item; // ebx
  DirectUI::Element *Ptr; // rsi
  int i; // [rsp+58h] [rbp+10h] BYREF

  v3 = this;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( (Microsoft_Windows_ShareMedia_ControlPanelEnableBits & 1) != 0 )
  {
    McTemplateU0zq_EventWriteTransfer(this, ShareMediaCPL_RemoveDevice_Start, a2, 0);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
    goto LABEL_23;
  v5 = a2;
  v6 = 0x7FFFFFFF;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  this = (CShareWithList *)((0x7FFFFFFF - (_DWORD)v6) & (unsigned int)-(v6 != 0));
  if ( (v6 != 0 ? 0x7FFFFFFF - (_DWORD)v6 : 0) != 0 )
  {
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
      WPP_SF_S(v4[2], 143, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, a2);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 72));
    i = -1;
    Item = CShareWithList::FindItem(v3, a2, &i);
    if ( Item )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 72));
    }
    else
    {
      Ptr = (DirectUI::Element *)DPA_GetPtr(*((HDPA *)v3 + 3), i);
      if ( Ptr )
      {
        Item = 0;
        DPA_DeletePtr(*((HDPA *)v3 + 3), i);
      }
      else
      {
        Item = -2147467259;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 72));
      if ( (Item & 0x80000000) == 0 && (*((_BYTE *)Ptr + 151) & 4) == 0 )
        DirectUI::Element::Destroy(Ptr, 1);
    }
    v4 = WPP_GLOBAL_Control;
  }
  else
  {
LABEL_23:
    Item = -2147467261;
  }
  if ( (Microsoft_Windows_ShareMedia_ControlPanelEnableBits & 1) != 0 )
  {
    McTemplateU0zq_EventWriteTransfer(this, ShareMediaCPL_RemoveDevice_Stop, a2, Item);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_d(v4[2], 144, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, Item);
  return Item;
}

```

## disassembly

```asm
0x18000d338  mov     [rsp+arg_0], rbx
0x18000d33d  mov     [rsp+arg_10], rbp
0x18000d342  push    rsi
0x18000d343  push    rdi
0x18000d344  push    r12
0x18000d346  push    r14
0x18000d348  push    r15
0x18000d34a  sub     rsp, 20h
0x18000d34e  mov     rdi, rdx
0x18000d351  mov     r14, rcx
0x18000d354  mov     r10, cs:WPP_GLOBAL_Control
0x18000d35b  lea     r12, WPP_GLOBAL_Control
0x18000d362  cmp     r10, r12
0x18000d365  jz      short loc_18000D38A
0x18000d367  test    byte ptr [r10+1Ch], 20h
0x18000d36c  jz      short loc_18000D38A
0x18000d36e  mov     rcx, [r10+10h]
0x18000d372  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000d379  mov     edx, 8Eh
0x18000d37e  call    WPP_SF_
0x18000d383  mov     r10, cs:WPP_GLOBAL_Control
0x18000d38a  test    cs:Microsoft_Windows_ShareMedia_ControlPanelEnableBits, 1
0x18000d391  jz      short loc_18000D3AC
0x18000d393  xor     r9d, r9d
0x18000d396  lea     rdx, ShareMediaCPL_RemoveDevice_Start
0x18000d39d  mov     r8, rdi
0x18000d3a0  call    McTemplateU0zq_EventWriteTransfer
0x18000d3a5  mov     r10, cs:WPP_GLOBAL_Control
0x18000d3ac  xor     r15d, r15d
0x18000d3af  test    rdi, rdi
0x18000d3b2  jz      loc_18000D4AA
0x18000d3b8  mov     r9d, 7FFFFFFFh
0x18000d3be  mov     rax, rdi
0x18000d3c1  mov     r8d, r9d
0x18000d3c4  cmp     [rax], r15w
0x18000d3c8  jz      short loc_18000D3D4
0x18000d3ca  add     rax, 2
0x18000d3ce  sub     r8, 1
0x18000d3d2  jnz     short loc_18000D3C4
0x18000d3d4  sub     r9d, r8d
0x18000d3d7  mov     rax, r8
0x18000d3da  neg     rax
0x18000d3dd  mov     rdx, r8
0x18000d3e0  sbb     ecx, ecx
0x18000d3e2  and     ecx, r9d
0x18000d3e5  neg     rdx
0x18000d3e8  sbb     edx, edx
0x18000d3ea  and     edx, ecx
0x18000d3ec  neg     r8
0x18000d3ef  sbb     eax, eax
0x18000d3f1  test    edx, eax
0x18000d3f3  jbe     loc_18000D4AA
0x18000d3f9  cmp     r10, r12
0x18000d3fc  jz      short loc_18000D41D
0x18000d3fe  test    byte ptr [r10+1Ch], 8
0x18000d403  jz      short loc_18000D41D
0x18000d405  mov     rcx, [r10+10h]
0x18000d409  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000d410  mov     edx, 8Fh
0x18000d415  mov     r9, rdi
0x18000d418  call    WPP_SF_S
0x18000d41d  lea     rbp, [r14+48h]
0x18000d421  mov     rcx, rbp; lpCriticalSection
0x18000d424  call    cs:__imp_EnterCriticalSection
0x18000d42a  lea     r8, [rsp+48h+i]; int *
0x18000d42f  mov     [rsp+48h+i], 0FFFFFFFFh
0x18000d437  mov     rdx, rdi; unsigned __int16 *
0x18000d43a  mov     rcx, r14; this
0x18000d43d  call    ?FindItem@CShareWithList@@QEAAJPEAGPEAH@Z; CShareWithList::FindItem(ushort *,int *)
0x18000d442  mov     ebx, eax
0x18000d444  test    eax, eax
0x18000d446  jz      short loc_18000D45A
0x18000d448  mov     rcx, rbp; lpCriticalSection
0x18000d44b  call    cs:__imp_LeaveCriticalSection
0x18000d451  mov     r10, cs:WPP_GLOBAL_Control
0x18000d458  jmp     short loc_18000D4AF
0x18000d45a  movsxd  rdx, [rsp+48h+i]; i
0x18000d45f  mov     rcx, [r14+18h]; hdpa
0x18000d463  call    DPA_GetPtr
0x18000d468  mov     rsi, rax
0x18000d46b  test    rax, rax
0x18000d46e  jz      short loc_18000D482
0x18000d470  mov     edx, [rsp+48h+i]; i
0x18000d474  mov     ebx, r15d
0x18000d477  mov     rcx, [r14+18h]; hdpa
0x18000d47b  call    DPA_DeletePtr
0x18000d480  jmp     short loc_18000D487
0x18000d482  mov     ebx, 80004005h
0x18000d487  mov     rcx, rbp; lpCriticalSection
0x18000d48a  call    cs:__imp_LeaveCriticalSection
0x18000d490  test    ebx, ebx
0x18000d492  js      short loc_18000D451
0x18000d494  test    byte ptr [rsi+97h], 4
0x18000d49b  jnz     short loc_18000D451
0x18000d49d  mov     dl, 1
0x18000d49f  mov     rcx, rsi
0x18000d4a2  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x18000d4a8  jmp     short loc_18000D451
0x18000d4aa  mov     ebx, 80004003h
0x18000d4af  test    cs:Microsoft_Windows_ShareMedia_ControlPanelEnableBits, 1
0x18000d4b6  jz      short loc_18000D4D1
0x18000d4b8  mov     r9d, ebx
0x18000d4bb  lea     rdx, ShareMediaCPL_RemoveDevice_Stop
0x18000d4c2  mov     r8, rdi
0x18000d4c5  call    McTemplateU0zq_EventWriteTransfer
0x18000d4ca  mov     r10, cs:WPP_GLOBAL_Control
0x18000d4d1  cmp     r10, r12
0x18000d4d4  jz      short loc_18000D4F5
0x18000d4d6  test    byte ptr [r10+1Ch], 20h
0x18000d4db  jz      short loc_18000D4F5
0x18000d4dd  mov     rcx, [r10+10h]
0x18000d4e1  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000d4e8  mov     edx, 90h
0x18000d4ed  mov     r9d, ebx
0x18000d4f0  call    WPP_SF_d
0x18000d4f5  mov     rbp, [rsp+48h+arg_10]
0x18000d4fa  mov     eax, ebx
0x18000d4fc  mov     rbx, [rsp+48h+arg_0]
0x18000d501  add     rsp, 20h
0x18000d505  pop     r15
0x18000d507  pop     r14
0x18000d509  pop     r12
0x18000d50b  pop     rdi
0x18000d50c  pop     rsi
0x18000d50d  retn
```
