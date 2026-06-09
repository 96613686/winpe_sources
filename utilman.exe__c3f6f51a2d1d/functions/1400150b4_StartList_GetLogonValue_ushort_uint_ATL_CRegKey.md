# StartList::GetLogonValue(ushort *,uint,ATL::CRegKey &)

- ea: `0x1400150b4`
- end: `0x140015194`
- name: `?GetLogonValue@StartList@@CAJPEAGIAEAVCRegKey@ATL@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int, struct ATL::CRegKey *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014ffc`

## callees

- `0x14000ea8c`
- `0x14000ecdc`
- `0x1400150b4`
- `0x14001827c`

## string_xrefs

- `0x14001513f`: `Configuration`
- `0x1400150cf`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility`

## pseudocode

```c
__int64 __fastcall StartList::GetLogonValue(unsigned __int16 *a1, unsigned int a2, struct ATL::CRegKey *a3)
{
  int v5; // ebx
  __int64 v6; // r8
  unsigned int v8; // eax
  __int64 v9; // r8
  unsigned int v10; // [rsp+38h] [rbp+10h] BYREF

  v10 = a2;
  *a1 = 0;
  v5 = ATL::CRegKey::Open(a3, HKEY_LOCAL_MACHINE, StartList::_accessibilityKeyString, 0x20019u);
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, v6, (unsigned int)v5);
    if ( v5 > 0 )
      return (unsigned __int16)v5 | 0x80070000;
    return (unsigned int)v5;
  }
  else
  {
    v10 = 1024;
    v8 = ATL::CRegKey::QueryStringValue(a3, L"Configuration", a1, &v10);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, v9, v8);
      *a1 = 0;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1400150b4  mov     [rsp+arg_0], rbx
0x1400150b9  mov     [rsp+arg_10], rsi
0x1400150be  mov     [rsp+arg_8], edx
0x1400150c2  push    rdi
0x1400150c3  sub     rsp, 20h
0x1400150c7  mov     rsi, r8
0x1400150ca  xor     eax, eax
0x1400150cc  mov     [rcx], ax
0x1400150cf  lea     r8, ?_accessibilityKeyString@StartList@@0PAGA; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400150d6  mov     rdi, rcx
0x1400150d9  mov     r9d, 20019h; unsigned int
0x1400150df  mov     rcx, rsi; this
0x1400150e2  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1400150e9  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400150ee  mov     ebx, eax
0x1400150f0  test    eax, eax
0x1400150f2  jz      short loc_14001512F
0x1400150f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400150fb  lea     rax, WPP_GLOBAL_Control
0x140015102  cmp     rcx, rax
0x140015105  jz      short loc_14001511E
0x140015107  test    byte ptr [rcx+1Ch], 8
0x14001510b  jz      short loc_14001511E
0x14001510d  mov     rcx, [rcx+10h]
0x140015111  mov     edx, 27h ; '''
0x140015116  mov     r9d, ebx
0x140015119  call    WPP_SF_d
0x14001511e  test    ebx, ebx
0x140015120  jle     short loc_14001512B
0x140015122  movzx   ebx, bx
0x140015125  or      ebx, 80070000h
0x14001512b  mov     eax, ebx
0x14001512d  jmp     short loc_140015183
0x14001512f  lea     r9, [rsp+28h+arg_8]; unsigned int *
0x140015134  mov     [rsp+28h+arg_8], 400h
0x14001513c  mov     r8, rdi; unsigned __int16 *
0x14001513f  lea     rdx, aConfiguration; "Configuration"
0x140015146  mov     rcx, rsi; this
0x140015149  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x14001514e  mov     r9d, eax
0x140015151  test    eax, eax
0x140015153  jz      short loc_140015181
0x140015155  mov     rcx, cs:WPP_GLOBAL_Control
0x14001515c  lea     rax, WPP_GLOBAL_Control
0x140015163  cmp     rcx, rax
0x140015166  jz      short loc_14001517C
0x140015168  test    byte ptr [rcx+1Ch], 8
0x14001516c  jz      short loc_14001517C
0x14001516e  mov     rcx, [rcx+10h]
0x140015172  mov     edx, 28h ; '('
0x140015177  call    WPP_SF_d
0x14001517c  xor     eax, eax
0x14001517e  mov     [rdi], ax
0x140015181  xor     eax, eax
0x140015183  mov     rbx, [rsp+28h+arg_0]
0x140015188  mov     rsi, [rsp+28h+arg_10]
0x14001518d  add     rsp, 20h
0x140015191  pop     rdi
0x140015192  retn
```
