# CShareWithList::IsDeviceOnCurrentNetwork(CDeviceSettings *)

- ea: `0x18000ad74`
- end: `0x18000ae8d`
- name: `?IsDeviceOnCurrentNetwork@CShareWithList@@QEAAHPEAVCDeviceSettings@@@Z`
- size: `281`
- prototype: `int(CShareWithList *__hidden this, struct CDeviceSettings *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18000a058`

## callees

- `0x180003860`
- `0x180003888`
- `0x180004c40`
- `0x18000ad74`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000aded`
- `KERNEL32!lstrcmpiW` at `0x18000aded`
- `ole32!CoTaskMemFree` at `0x18000ae51`
- `ole32!CoTaskMemFree` at `0x18000ae51`

## pseudocode

```c
__int64 __fastcall CShareWithList::IsDeviceOnCurrentNetwork(CShareWithList *this, struct CDeviceSettings *a2)
{
  _QWORD *v4; // rcx
  unsigned int v5; // ebx
  _QWORD *v6; // rcx
  LPCWSTR lpString1; // [rsp+58h] [rbp+10h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  v5 = 1;
  if ( a2 )
  {
    lpString1 = 0;
    if ( CDeviceSettings::GetID(a2, (unsigned __int16 **)&lpString1) >= 0 )
    {
      if ( lstrcmpiW(lpString1, L"00-00-00-00-00-00") && *((_DWORD *)this + 31) )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
            v6 = WPP_GLOBAL_Control;
          }
          if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
            WPP_SF_(v6[2], 33, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids);
        }
        v5 = *((_DWORD *)a2 + 25);
      }
      CoTaskMemFree((LPVOID)lpString1);
    }
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_d(v4[2], 135, &WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x18000ad74  push    rbx
0x18000ad76  push    rsi
0x18000ad77  push    rdi
0x18000ad78  push    r14
0x18000ad7a  sub     rsp, 28h
0x18000ad7e  mov     rdi, rdx
0x18000ad81  mov     rsi, rcx
0x18000ad84  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad8b  lea     r14, WPP_GLOBAL_Control
0x18000ad92  cmp     rcx, r14
0x18000ad95  jz      short loc_18000ADB9
0x18000ad97  test    byte ptr [rcx+1Ch], 20h
0x18000ad9b  jz      short loc_18000ADB9
0x18000ad9d  mov     rcx, [rcx+10h]
0x18000ada1  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000ada8  mov     edx, 86h
0x18000adad  call    WPP_SF_
0x18000adb2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000adb9  mov     ebx, 1
0x18000adbe  test    rdi, rdi
0x18000adc1  jz      loc_18000AE5E
0x18000adc7  lea     rdx, [rsp+48h+lpString1]; unsigned __int16 **
0x18000adcc  mov     [rsp+48h+lpString1], 0
0x18000add5  mov     rcx, rdi; this
0x18000add8  call    ?GetID@CDeviceSettings@@QEAAJPEAPEAG@Z; CDeviceSettings::GetID(ushort * *)
0x18000addd  test    eax, eax
0x18000addf  js      short loc_18000AE57
0x18000ade1  mov     rcx, [rsp+48h+lpString1]; lpString1
0x18000ade6  lea     rdx, psz; "00-00-00-00-00-00"
0x18000aded  call    cs:__imp_lstrcmpiW
0x18000adf3  test    eax, eax
0x18000adf5  jz      short loc_18000AE4C
0x18000adf7  cmp     dword ptr [rsi+7Ch], 0
0x18000adfb  jz      short loc_18000AE4C
0x18000adfd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae04  cmp     rcx, r14
0x18000ae07  jz      short loc_18000AE49
0x18000ae09  test    byte ptr [rcx+1Ch], 20h
0x18000ae0d  jz      short loc_18000AE29
0x18000ae0f  mov     rcx, [rcx+10h]
0x18000ae13  lea     edx, [rbx+1Fh]
0x18000ae16  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x18000ae1d  call    WPP_SF_
0x18000ae22  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae29  cmp     rcx, r14
0x18000ae2c  jz      short loc_18000AE49
0x18000ae2e  test    byte ptr [rcx+1Ch], 20h
0x18000ae32  jz      short loc_18000AE49
0x18000ae34  mov     rcx, [rcx+10h]
0x18000ae38  lea     r8, WPP_d9b8941d15ae3a5ad4fdf53b8af56098_Traceguids
0x18000ae3f  mov     edx, 21h ; '!'
0x18000ae44  call    WPP_SF_
0x18000ae49  mov     ebx, [rdi+64h]
0x18000ae4c  mov     rcx, [rsp+48h+lpString1]; pv
0x18000ae51  call    cs:__imp_CoTaskMemFree
0x18000ae57  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae5e  cmp     rcx, r14
0x18000ae61  jz      short loc_18000AE81
0x18000ae63  test    byte ptr [rcx+1Ch], 20h
0x18000ae67  jz      short loc_18000AE81
0x18000ae69  mov     rcx, [rcx+10h]
0x18000ae6d  lea     r8, WPP_59386dd0a0913b67da6dc13cee28e88f_Traceguids
0x18000ae74  mov     edx, 87h
0x18000ae79  mov     r9d, ebx
0x18000ae7c  call    WPP_SF_d
0x18000ae81  mov     eax, ebx
0x18000ae83  add     rsp, 28h
0x18000ae87  pop     r14
0x18000ae89  pop     rdi
0x18000ae8a  pop     rsi
0x18000ae8b  pop     rbx
0x18000ae8c  retn
```
