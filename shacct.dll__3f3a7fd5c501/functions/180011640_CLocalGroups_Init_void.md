# CLocalGroups::_Init(void)

- ea: `0x180011640`
- end: `0x18001172e`
- name: `?_Init@CLocalGroups@@EEAAJXZ`
- size: `238`
- prototype: `__int64 __fastcall(CLocalGroups *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800037e0`
- `0x18000b9e0`
- `0x180011640`
- `0x1800125e8`
- `0x180012f18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800116b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001171c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800116b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001171c`

## pseudocode

```c
__int64 __fastcall CLocalGroups::_Init(CLocalGroups *this)
{
  int v1; // ebx
  int v3; // eax
  int v4; // eax
  LPVOID pv; // [rsp+50h] [rbp+8h] BYREF

  v1 = 0;
  pv = 0;
  if ( !*((_QWORD *)this + 4) )
  {
    v1 = CSGetAccountDomainSid(&pv);
    if ( v1 >= 0 )
    {
      v3 = CSGetGroupRIDEnumeration(pv, (char *)this + 32, (char *)this + 24);
      v1 = v3;
      if ( v3 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
          (unsigned int)v3);
      }
      CoTaskMemFree(pv);
    }
  }
  if ( !*((_QWORD *)this + 2) )
  {
    v1 = CSGetBuiltInDomainSid(&pv);
    if ( v1 >= 0 )
    {
      v4 = CSGetGroupRIDEnumeration(pv, (char *)this + 16, (char *)this + 12);
      v1 = v4;
      if ( v4 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids,
          (unsigned int)v4);
      }
      CoTaskMemFree(pv);
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180011640  push    rbx
0x180011642  push    rsi
0x180011643  push    rdi
0x180011644  push    r14
0x180011646  sub     rsp, 28h
0x18001164a  xor     ebx, ebx
0x18001164c  lea     r14, WPP_GLOBAL_Control
0x180011653  mov     rdi, rcx
0x180011656  mov     [rsp+48h+pv], rbx
0x18001165b  cmp     [rcx+20h], rbx
0x18001165f  jnz     short loc_1800116BE
0x180011661  lea     rcx, [rsp+48h+pv]
0x180011666  call    CSGetAccountDomainSid
0x18001166b  mov     ebx, eax
0x18001166d  test    eax, eax
0x18001166f  js      short loc_1800116BE
0x180011671  mov     rcx, [rsp+48h+pv]
0x180011676  lea     r8, [rdi+18h]
0x18001167a  lea     rdx, [rdi+20h]
0x18001167e  call    CSGetGroupRIDEnumeration
0x180011683  mov     ebx, eax
0x180011685  test    eax, eax
0x180011687  jns     short loc_1800116B3
0x180011689  mov     rcx, cs:WPP_GLOBAL_Control
0x180011690  cmp     rcx, r14
0x180011693  jz      short loc_1800116B3
0x180011695  test    byte ptr [rcx+1Ch], 2
0x180011699  jz      short loc_1800116B3
0x18001169b  mov     rcx, [rcx+10h]
0x18001169f  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x1800116a6  mov     edx, 1Ah
0x1800116ab  mov     r9d, eax
0x1800116ae  call    WPP_SF_d
0x1800116b3  mov     rcx, [rsp+48h+pv]; pv
0x1800116b8  call    cs:__imp_CoTaskMemFree
0x1800116be  cmp     qword ptr [rdi+10h], 0
0x1800116c3  jnz     short loc_180011722
0x1800116c5  lea     rcx, [rsp+48h+pv]
0x1800116ca  call    CSGetBuiltInDomainSid
0x1800116cf  mov     ebx, eax
0x1800116d1  test    eax, eax
0x1800116d3  js      short loc_180011722
0x1800116d5  mov     rcx, [rsp+48h+pv]
0x1800116da  lea     r8, [rdi+0Ch]
0x1800116de  lea     rdx, [rdi+10h]
0x1800116e2  call    CSGetGroupRIDEnumeration
0x1800116e7  mov     ebx, eax
0x1800116e9  test    eax, eax
0x1800116eb  jns     short loc_180011717
0x1800116ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800116f4  cmp     rcx, r14
0x1800116f7  jz      short loc_180011717
0x1800116f9  test    byte ptr [rcx+1Ch], 2
0x1800116fd  jz      short loc_180011717
0x1800116ff  mov     rcx, [rcx+10h]
0x180011703  lea     r8, WPP_b7edbcfa3c6c396011b8fcbeff20f182_Traceguids
0x18001170a  mov     edx, 1Bh
0x18001170f  mov     r9d, eax
0x180011712  call    WPP_SF_d
0x180011717  mov     rcx, [rsp+48h+pv]; pv
0x18001171c  call    cs:__imp_CoTaskMemFree
0x180011722  mov     eax, ebx
0x180011724  add     rsp, 28h
0x180011728  pop     r14
0x18001172a  pop     rdi
0x18001172b  pop     rsi
0x18001172c  pop     rbx
0x18001172d  retn
```
