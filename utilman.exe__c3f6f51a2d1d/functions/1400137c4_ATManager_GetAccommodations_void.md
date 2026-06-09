# ATManager::GetAccommodations(void)

- ea: `0x1400137c4`
- end: `0x140013902`
- name: `?GetAccommodations@ATManager@@QEAAAEBV?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@XZ`
- size: `318`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140015468`
- `0x14001bcec`

## callees

- `0x140002480`
- `0x14000d75c`
- `0x14000ea8c`
- `0x1400137c4`
- `0x140013908`
- `0x140018ac8`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x1400138c1`
- `ADVAPI32!RegEnumKeyExW` at `0x1400138c1`

## string_xrefs

- `0x140013807`: `Software\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATManager::GetAccommodations(__int64 a1)
{
  DWORD v2; // esi
  DWORD i; // edx
  __int64 v4; // rax
  __int64 *v5; // rcx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  struct Accommodation *v9; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[64]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  if ( !(unsigned int)ATL::CRegKey::Open(
                        (ATL::CRegKey *)hKey,
                        HKEY_LOCAL_MACHINE,
                        L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Accessibility\\ATs",
                        0x20019u) )
  {
    v2 = 0;
    for ( i = 0; ; i = v2 )
    {
      cchName = 64;
      if ( RegEnumKeyExW(hKey[0], i, Name, &cchName, 0, 0, 0, 0) == 259 )
        break;
      v9 = Accommodation::Open(Name);
      if ( v9 )
      {
        v4 = ATL::CAtlList<Accommodation *,ATL::CElementTraits<Accommodation *>>::NewNode(
               a1 + 304,
               &v9,
               *(_QWORD *)(a1 + 312));
        v5 = *(__int64 **)(a1 + 312);
        if ( v5 )
          *v5 = v4;
        else
          *(_QWORD *)(a1 + 304) = v4;
        *(_QWORD *)(a1 + 312) = v4;
      }
      ++v2;
    }
  }
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  return a1 + 304;
}

```

## disassembly

```asm
0x1400137c4  push    rbp
0x1400137c6  push    rbx
0x1400137c7  push    rsi
0x1400137c8  push    rdi
0x1400137c9  lea     rbp, [rsp-8]
0x1400137ce  sub     rsp, 108h
0x1400137d5  mov     rax, cs:__security_cookie
0x1400137dc  xor     rax, rsp
0x1400137df  mov     [rbp+20h+var_30], rax
0x1400137e3  mov     rdi, rcx
0x1400137e6  mov     [rsp+120h+hKey], 0
0x1400137ef  mov     [rsp+120h+var_D0], 0
0x1400137f8  mov     [rsp+120h+var_C8], 0
0x140013801  mov     r9d, 20019h; unsigned int
0x140013807  lea     r8, aSoftwareMicros_7; "Software\\Microsoft\\Windows NT\\Curren"...
0x14001380e  mov     rdx, 0FFFFFFFF80000002h; hKey
0x140013815  lea     rcx, [rsp+120h+hKey]; this
0x14001381a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14001381f  test    eax, eax
0x140013821  jnz     loc_1400138D8
0x140013827  xor     esi, esi
0x140013829  mov     [rsp+120h+lpftLastWriteTime], rsi
0x14001382e  mov     [rsp+120h+lpcchClass], rsi
0x140013833  mov     [rsp+120h+lpClass], rsi
0x140013838  mov     [rsp+120h+lpReserved], rsi
0x14001383d  xor     edx, edx
0x14001383f  jmp     short loc_1400138AA
0x140013841  lea     rcx, [rsp+120h+Name]; unsigned __int16 *
0x140013846  call    ?Open@Accommodation@@SAPEAV1@PEBG@Z; Accommodation::Open(ushort const *)
0x14001384b  mov     [rsp+120h+var_C0], rax
0x140013850  test    rax, rax
0x140013853  jz      short loc_140013882
0x140013855  lea     rbx, [rdi+130h]
0x14001385c  mov     r8, [rbx+8]
0x140013860  lea     rdx, [rsp+120h+var_C0]
0x140013865  mov     rcx, rbx
0x140013868  call    ?NewNode@?$CAtlList@PEAVAccommodation@@V?$CElementTraits@PEAVAccommodation@@@ATL@@@ATL@@AEAAPEAVCNode@12@AEBQEAVAccommodation@@PEAV312@1@Z; ATL::CAtlList<Accommodation *,ATL::CElementTraits<Accommodation *>>::NewNode(Accommodation * const &,ATL::CAtlList<Accommodation *,ATL::CElementTraits<Accommodation *>>::CNode *,ATL::CAtlList<Accommodation *,ATL::CElementTraits<Accommodation *>>::CNode *)
0x14001386d  mov     rcx, [rbx+8]
0x140013871  test    rcx, rcx
0x140013874  jz      short loc_14001387B
0x140013876  mov     [rcx], rax
0x140013879  jmp     short loc_14001387E
0x14001387b  mov     [rbx], rax
0x14001387e  mov     [rbx+8], rax
0x140013882  inc     esi
0x140013884  mov     [rsp+120h+lpftLastWriteTime], 0; lpftLastWriteTime
0x14001388d  mov     [rsp+120h+lpcchClass], 0; lpcchClass
0x140013896  mov     [rsp+120h+lpClass], 0; lpClass
0x14001389f  mov     [rsp+120h+lpReserved], 0; lpReserved
0x1400138a8  mov     edx, esi; dwIndex
0x1400138aa  mov     [rsp+120h+cchName], 40h ; '@'
0x1400138b2  lea     r9, [rsp+120h+cchName]; lpcchName
0x1400138b7  lea     r8, [rsp+120h+Name]; lpName
0x1400138bc  mov     rcx, [rsp+120h+hKey]; hKey
0x1400138c1  call    cs:__imp_RegEnumKeyExW
0x1400138c8  nop     dword ptr [rax+rax+00h]
0x1400138cd  cmp     eax, 103h
0x1400138d2  jnz     loc_140013841
0x1400138d8  lea     rcx, [rsp+120h+hKey]; this
0x1400138dd  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1400138e2  lea     rax, [rdi+130h]
0x1400138e9  mov     rcx, [rbp+20h+var_30]
0x1400138ed  xor     rcx, rsp; StackCookie
0x1400138f0  call    __security_check_cookie
0x1400138f5  add     rsp, 108h
0x1400138fc  pop     rdi
0x1400138fd  pop     rsi
0x1400138fe  pop     rbx
0x1400138ff  pop     rbp
0x140013900  retn
```
