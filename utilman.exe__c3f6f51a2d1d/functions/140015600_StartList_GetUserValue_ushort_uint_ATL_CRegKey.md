# StartList::GetUserValue(ushort *,uint,ATL::CRegKey &)

- ea: `0x140015600`
- end: `0x140015717`
- name: `?GetUserValue@StartList@@AEAAJPEAGIAEAVCRegKey@ATL@@@Z`
- size: `279`
- prototype: `int(StartList *__hidden this, unsigned __int16 *, unsigned int, struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140015fb8`

## callees

- `0x14000ea8c`
- `0x14000ecdc`
- `0x140015600`
- `0x14001827c`

## string_xrefs

- `0x14001568f`: `Configuration`
- `0x140015617`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`

## pseudocode

```c
__int64 __fastcall StartList::GetUserValue(
        StartList *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct ATL::CRegKey *a4)
{
  int v6; // ebx
  __int64 v7; // r8
  unsigned int v9; // eax
  __int64 v10; // r8
  unsigned int v11; // [rsp+40h] [rbp+18h] BYREF

  v11 = a3;
  *a2 = 0;
  v6 = ATL::CRegKey::Open(a4, HKEY_CURRENT_USER, StartList::_accessibilityKeyString, 0x20019u);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, v7, (unsigned int)v6);
    if ( v6 > 0 )
      return (unsigned __int16)v6 | 0x80070000;
    return (unsigned int)v6;
  }
  else
  {
    v11 = 1024;
    v9 = ATL::CRegKey::QueryStringValue(a4, L"Configuration", a2, &v11);
    if ( v9 == 2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v9 + 35, v10, v9);
      return 2147942402LL;
    }
    else
    {
      if ( v9 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, v10, v9);
        *a2 = 0;
      }
      return 0;
    }
  }
}

```

## disassembly

```asm
0x140015600  mov     [rsp+arg_0], rbx
0x140015605  mov     [rsp+arg_8], rsi
0x14001560a  mov     [rsp+arg_10], r8d
0x14001560f  push    rdi
0x140015610  sub     rsp, 20h
0x140015614  mov     rsi, r9
0x140015617  lea     r8, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001561e  xor     eax, eax
0x140015620  mov     rdi, rdx
0x140015623  mov     [rdx], ax
0x140015626  mov     r9d, 20019h; unsigned int
0x14001562c  mov     rdx, 0FFFFFFFF80000001h; hKey
0x140015633  mov     rcx, rsi; this
0x140015636  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001563b  mov     ebx, eax
0x14001563d  test    eax, eax
0x14001563f  jz      short loc_14001567F
0x140015641  mov     rcx, cs:WPP_GLOBAL_Control
0x140015648  lea     rax, WPP_GLOBAL_Control
0x14001564f  cmp     rcx, rax
0x140015652  jz      short loc_14001566B
0x140015654  test    byte ptr [rcx+1Ch], 8
0x140015658  jz      short loc_14001566B
0x14001565a  mov     rcx, [rcx+10h]
0x14001565e  mov     edx, 24h ; '$'
0x140015663  mov     r9d, ebx
0x140015666  call    WPP_SF_d
0x14001566b  test    ebx, ebx
0x14001566d  jle     short loc_140015678
0x14001566f  movzx   ebx, bx
0x140015672  or      ebx, 80070000h
0x140015678  mov     eax, ebx
0x14001567a  jmp     loc_140015706
0x14001567f  lea     r9, [rsp+28h+arg_10]; unsigned int *
0x140015684  mov     [rsp+28h+arg_10], 400h
0x14001568c  mov     r8, rdi; unsigned __int16 *
0x14001568f  lea     rdx, aConfiguration; "Configuration"
0x140015696  mov     rcx, rsi; this
0x140015699  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14001569e  mov     r9d, eax
0x1400156a1  cmp     eax, 2
0x1400156a4  jnz     short loc_1400156D3
0x1400156a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400156ad  lea     rax, WPP_GLOBAL_Control
0x1400156b4  cmp     rcx, rax
0x1400156b7  jz      short loc_1400156CC
0x1400156b9  test    byte ptr [rcx+1Ch], 8
0x1400156bd  jz      short loc_1400156CC
0x1400156bf  mov     rcx, [rcx+10h]
0x1400156c3  lea     edx, [r9+23h]
0x1400156c7  call    WPP_SF_d
0x1400156cc  mov     eax, 80070002h
0x1400156d1  jmp     short loc_140015706
0x1400156d3  test    r9d, r9d
0x1400156d6  jz      short loc_140015704
0x1400156d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400156df  lea     rax, WPP_GLOBAL_Control
0x1400156e6  cmp     rcx, rax
0x1400156e9  jz      short loc_1400156FF
0x1400156eb  test    byte ptr [rcx+1Ch], 8
0x1400156ef  jz      short loc_1400156FF
0x1400156f1  mov     rcx, [rcx+10h]
0x1400156f5  mov     edx, 26h ; '&'
0x1400156fa  call    WPP_SF_d
0x1400156ff  xor     eax, eax
0x140015701  mov     [rdi], ax
0x140015704  xor     eax, eax
0x140015706  mov     rbx, [rsp+28h+arg_0]
0x14001570b  mov     rsi, [rsp+28h+arg_8]
0x140015710  add     rsp, 20h
0x140015714  pop     rdi
0x140015715  retn
```
