# GetInstanceOfJsonHelper(IJsonHelper * *)

- ea: `0x180012a78`
- end: `0x180012c16`
- name: `?GetInstanceOfJsonHelper@@YAJPEAPEAVIJsonHelper@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(struct IJsonHelper **)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000fec0`
- `0x180011310`

## callees

- `0x180007a64`
- `0x180012a78`
- `0x180014b34`
- `0x180014bb0`
- `0x180015488`
- `0x180016010`

## string_xrefs

- `0x180012ab1`: `JsonHelper`
- `0x180012bdb`: `JsonHelper`
- `0x180012b6b`: `spJsonHelper->Initialize failed`

## pseudocode

```c
__int64 __fastcall GetInstanceOfJsonHelper(struct IJsonHelper **a1)
{
  struct IJsonHelper *v2; // rax
  __int64 v3; // rdx
  struct IJsonHelper *v4; // rbx
  __int64 v5; // rdx
  int v6; // edi
  int ActivityIdPrefix; // eax
  int v8; // eax

  v2 = (struct IJsonHelper *)operator new(0x58u);
  v4 = v2;
  if ( v2 )
  {
    *(_QWORD *)v2 = &IJsonHelper::`vftable';
    *((_DWORD *)v2 + 8) = -607474739;
    *((_QWORD *)v2 + 3) = "JsonHelper";
    *((_DWORD *)v2 + 9) = 1;
    *((_QWORD *)v2 + 1) = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
    *((_QWORD *)v2 + 2) = &CTSUnknown::`vftable'{for `CTSObject'};
    *((_DWORD *)v2 + 12) = 0;
    *((_QWORD *)v2 + 5) = (char *)v2 + 8;
    *(_QWORD *)v2 = &JsonHelper::`vftable';
    *((_QWORD *)v2 + 1) = &JsonHelper::`vftable'{for `INonDelegatingUnknown'};
    *((_QWORD *)v2 + 2) = &JsonHelper::`vftable'{for `CTSObject'};
    *((_QWORD *)v2 + 7) = 0;
    *((_QWORD *)v2 + 8) = 0;
    *((_QWORD *)v2 + 9) = 0;
    *((_BYTE *)v2 + 80) = 0;
    (*(void (__fastcall **)(struct IJsonHelper *))(*(_QWORD *)v2 + 8LL))(v2);
    v6 = (*(__int64 (__fastcall **)(_QWORD *))(*((_QWORD *)v4 + 2) + 16LL))((_QWORD *)v4 + 2);
    if ( v6 >= 0 )
    {
      *a1 = v4;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v5);
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
          ActivityIdPrefix,
          (__int64)"spJsonHelper->Initialize failed",
          v6);
      }
      (*(void (__fastcall **)(struct IJsonHelper *))(*(_QWORD *)v4 + 16LL))(v4);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v8 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v3);
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
        v8,
        (__int64)"JsonHelper");
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180012a78  mov     [rsp+arg_0], rbx
0x180012a7d  mov     [rsp+arg_8], rsi
0x180012a82  push    rdi
0x180012a83  sub     rsp, 30h
0x180012a87  mov     rsi, rcx
0x180012a8a  mov     ecx, 58h ; 'X'; Size
0x180012a8f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012a94  mov     rbx, rax
0x180012a97  test    rax, rax
0x180012a9a  jz      loc_180012BB0
0x180012aa0  lea     rdx, [rbx+8]
0x180012aa4  mov     rcx, rbx
0x180012aa7  lea     rax, ??_7IJsonHelper@@6B@; const IJsonHelper::`vftable'
0x180012aae  mov     [rbx], rax
0x180012ab1  lea     r8, aJsonhelper; "JsonHelper"
0x180012ab8  mov     dword ptr [rdx+18h], 0DBCAABCDh
0x180012abf  lea     rax, ??_7CTSUnknown@@6BINonDelegatingUnknown@@@; const CTSUnknown::`vftable'{for `INonDelegatingUnknown'}
0x180012ac6  mov     [rdx+10h], r8
0x180012aca  mov     dword ptr [rdx+1Ch], 1
0x180012ad1  mov     [rdx], rax
0x180012ad4  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x180012adb  mov     [rdx+8], rax
0x180012adf  lea     rax, ??_7JsonHelper@@6B@; const JsonHelper::`vftable'
0x180012ae6  mov     dword ptr [rdx+28h], 0
0x180012aed  mov     [rdx+20h], rdx
0x180012af1  mov     [rbx], rax
0x180012af4  lea     rax, ??_7JsonHelper@@6BINonDelegatingUnknown@@@; const JsonHelper::`vftable'{for `INonDelegatingUnknown'}
0x180012afb  mov     [rdx], rax
0x180012afe  lea     rax, ??_7JsonHelper@@6BCTSObject@@@; const JsonHelper::`vftable'{for `CTSObject'}
0x180012b05  mov     [rbx+10h], rax
0x180012b09  mov     qword ptr [rbx+38h], 0
0x180012b11  mov     qword ptr [rbx+40h], 0
0x180012b19  mov     qword ptr [rbx+48h], 0
0x180012b21  mov     byte ptr [rbx+50h], 0
0x180012b25  mov     rax, [rbx]
0x180012b28  mov     rax, [rax+8]
0x180012b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b31  lea     rcx, [rbx+10h]
0x180012b35  mov     rax, [rcx]
0x180012b38  mov     rax, [rax+10h]
0x180012b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b41  mov     edi, eax
0x180012b43  test    eax, eax
0x180012b45  jns     short loc_180012BAB
0x180012b47  mov     rax, cs:WPP_GLOBAL_Control
0x180012b4e  lea     rcx, WPP_GLOBAL_Control
0x180012b55  cmp     rax, rcx
0x180012b58  jz      short loc_180012B9A
0x180012b5a  test    byte ptr [rax+1Ch], 8
0x180012b5e  jz      short loc_180012B9A
0x180012b60  cmp     byte ptr [rax+19h], 2
0x180012b64  jb      short loc_180012B9A
0x180012b66  call    RdpX_GetActivityIdPrefix
0x180012b6b  lea     rcx, aSpjsonhelperIn; "spJsonHelper->Initialize failed"
0x180012b72  mov     [rsp+38h+var_10], edi
0x180012b76  mov     [rsp+38h+var_18], rcx
0x180012b7b  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180012b82  mov     rcx, cs:WPP_GLOBAL_Control
0x180012b89  mov     edx, 3Dh ; '='
0x180012b8e  mov     r9d, eax
0x180012b91  mov     rcx, [rcx+10h]
0x180012b95  call    WPP_SF_DsD
0x180012b9a  mov     rax, [rbx]
0x180012b9d  mov     rcx, rbx
0x180012ba0  mov     rax, [rax+10h]
0x180012ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ba9  jmp     short loc_180012C04
0x180012bab  mov     [rsi], rbx
0x180012bae  jmp     short loc_180012C04
0x180012bb0  mov     rax, cs:WPP_GLOBAL_Control
0x180012bb7  lea     rcx, WPP_GLOBAL_Control
0x180012bbe  cmp     rax, rcx
0x180012bc1  jz      short loc_180012BFF
0x180012bc3  test    byte ptr [rax+1Ch], 8
0x180012bc7  jz      short loc_180012BFF
0x180012bc9  cmp     byte ptr [rax+19h], 2
0x180012bcd  jb      short loc_180012BFF
0x180012bcf  call    RdpX_GetActivityIdPrefix
0x180012bd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bdb  lea     r8, aJsonhelper; "JsonHelper"
0x180012be2  mov     [rsp+38h+var_18], r8
0x180012be7  mov     edx, 3Ch ; '<'
0x180012bec  mov     r9d, eax
0x180012bef  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180012bf6  mov     rcx, [rcx+10h]
0x180012bfa  call    WPP_SF_Ds
0x180012bff  mov     edi, 8007000Eh
0x180012c04  mov     rbx, [rsp+38h+arg_0]
0x180012c09  mov     eax, edi
0x180012c0b  mov     rsi, [rsp+38h+arg_8]
0x180012c10  add     rsp, 30h
0x180012c14  pop     rdi
0x180012c15  retn
```
