# CShareWithListItemBase::_InitializeIcon(void)

- ea: `0x18000e760`
- end: `0x18000e873`
- name: `?_InitializeIcon@CShareWithListItemBase@@MEAAJXZ`
- size: `275`
- prototype: `__int64 __fastcall(CShareWithListItemBase *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180003860`
- `0x180003888`
- `0x18000449c`
- `0x18000e760`

## import_xrefs

- `GDI32!DeleteObject` at `0x18000e837`
- `GDI32!DeleteObject` at `0x18000e837`
- `DUI70!StrToID` at `0x18000e7a2`
- `DUI70!StrToID` at `0x18000e7a2`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000e7ae`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18000e7ae`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000e809`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18000e81c`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x18000e81c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000e825`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000e825`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x18000e7fb`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x18000e7fb`

## pseudocode

```c
__int64 __fastcall CShareWithListItemBase::_InitializeIcon(const WCHAR ***this)
{
  unsigned __int16 v2; // ax
  __int64 v3; // rdx
  DirectUI::Element *Descendent; // rsi
  int v5; // r8d
  int DeviceIcon; // ebx
  const WCHAR **v7; // rcx
  struct DirectUI::Value *Graphic; // rax
  DirectUI::Value *v9; // rdi
  HGDIOBJ ho; // [rsp+68h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 199, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
  v2 = StrToID(L"ShareIcon");
  Descendent = DirectUI::Element::FindDescendent((DirectUI::Element *)this, v2);
  if ( Descendent )
  {
    v7 = this[27];
    ho = 0;
    DeviceIcon = CDeviceSettings::GetDeviceIcon(v7, v3, v5, (HBITMAP *)&ho);
    if ( DeviceIcon >= 0 )
    {
      Graphic = DirectUI::Value::CreateGraphic((HBITMAP)ho, 2u, 0xFFFFFFFF, 0, 0, 0);
      v9 = Graphic;
      if ( Graphic )
      {
        DeviceIcon = 0;
        DirectUI::Element::SetValue(
          Descendent,
          (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
          1,
          Graphic);
        DirectUI::Value::Release(v9);
      }
      else
      {
        DeviceIcon = -2147467259;
        DeleteObject(ho);
      }
    }
  }
  else
  {
    DeviceIcon = -2147467259;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      200,
      &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids,
      (unsigned int)DeviceIcon);
  return (unsigned int)DeviceIcon;
}

```

## disassembly

```asm
0x18000e760  push    rbx
0x18000e762  push    rsi
0x18000e763  push    rdi
0x18000e764  push    r14
0x18000e766  sub     rsp, 38h
0x18000e76a  mov     rbx, rcx
0x18000e76d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e774  lea     r14, WPP_GLOBAL_Control
0x18000e77b  cmp     rcx, r14
0x18000e77e  jz      short loc_18000E79B
0x18000e780  test    byte ptr [rcx+1Ch], 20h
0x18000e784  jz      short loc_18000E79B
0x18000e786  mov     rcx, [rcx+10h]
0x18000e78a  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000e791  mov     edx, 0C7h
0x18000e796  call    WPP_SF_
0x18000e79b  lea     rcx, aShareicon; "ShareIcon"
0x18000e7a2  call    cs:__imp_StrToID
0x18000e7a8  movzx   edx, ax
0x18000e7ab  mov     rcx, rbx
0x18000e7ae  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18000e7b4  mov     rsi, rax
0x18000e7b7  test    rax, rax
0x18000e7ba  jnz     short loc_18000E7C3
0x18000e7bc  mov     ebx, 80004005h
0x18000e7c1  jmp     short loc_18000E83D
0x18000e7c3  mov     rcx, [rbx+0D8h]; this
0x18000e7ca  lea     r9, [rsp+58h+ho]; HBITMAP *
0x18000e7cf  mov     [rsp+58h+ho], 0
0x18000e7d8  call    ?GetDeviceIcon@CDeviceSettings@@QEAAJHHPEAPEAUHBITMAP__@@@Z; CDeviceSettings::GetDeviceIcon(int,int,HBITMAP__ * *)
0x18000e7dd  mov     ebx, eax
0x18000e7df  test    eax, eax
0x18000e7e1  js      short loc_18000E83D
0x18000e7e3  mov     rcx, [rsp+58h+ho]
0x18000e7e8  xor     r9d, r9d
0x18000e7eb  mov     [rsp+58h+var_30], 0
0x18000e7f0  or      r8d, 0FFFFFFFFh
0x18000e7f4  mov     dl, 2
0x18000e7f6  mov     [rsp+58h+var_38], 0
0x18000e7fb  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z; DirectUI::Value::CreateGraphic(HBITMAP__ *,uchar,uint,bool,bool,bool)
0x18000e801  mov     rdi, rax
0x18000e804  test    rax, rax
0x18000e807  jz      short loc_18000E82D
0x18000e809  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x18000e810  xor     ebx, ebx
0x18000e812  mov     r9, rax
0x18000e815  mov     rcx, rsi
0x18000e818  lea     r8d, [rbx+1]
0x18000e81c  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x18000e822  mov     rcx, rdi
0x18000e825  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000e82b  jmp     short loc_18000E83D
0x18000e82d  mov     rcx, [rsp+58h+ho]; ho
0x18000e832  mov     ebx, 80004005h
0x18000e837  call    cs:__imp_DeleteObject
0x18000e83d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e844  cmp     rcx, r14
0x18000e847  jz      short loc_18000E867
0x18000e849  test    byte ptr [rcx+1Ch], 20h
0x18000e84d  jz      short loc_18000E867
0x18000e84f  mov     rcx, [rcx+10h]
0x18000e853  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000e85a  mov     edx, 0C8h
0x18000e85f  mov     r9d, ebx
0x18000e862  call    WPP_SF_d
0x18000e867  mov     eax, ebx
0x18000e869  add     rsp, 38h
0x18000e86d  pop     r14
0x18000e86f  pop     rdi
0x18000e870  pop     rsi
0x18000e871  pop     rbx
0x18000e872  retn
```
