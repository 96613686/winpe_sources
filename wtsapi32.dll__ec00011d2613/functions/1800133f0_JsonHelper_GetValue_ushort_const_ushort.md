# JsonHelper::GetValue(ushort const *,ushort * *)

- ea: `0x1800133f0`
- end: `0x1800135f6`
- name: `?GetValue@JsonHelper@@UEAAJPEBGPEAPEAG@Z`
- size: `518`
- prototype: `__int64 __fastcall(JsonHelper *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180006734`
- `0x180007a64`
- `0x18000e2e8`
- `0x180012230`
- `0x1800133f0`
- `0x180014b34`
- `0x180014bb0`
- `0x180015488`
- `0x1800155c0`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800134d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800134d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013430`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800135d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013430`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800135d2`

## string_xrefs

- `0x180013592`: `StringCchCopy failed!`
- `0x180013494`: `m_spJsonObj->GetNamedString failed!`

## pseudocode

```c
__int64 __fastcall JsonHelper::GetValue(JsonHelper *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 v3; // rdi
  __int64 (__fastcall *v5)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v6; // rax
  __int64 v7; // rdx
  int v8; // ebx
  int v9; // eax
  const unsigned __int16 *StringRawBuffer; // rbx
  unsigned __int16 *v11; // rax
  __int64 v12; // rdx
  unsigned __int16 *v13; // rdi
  int v14; // eax
  __int64 v15; // rdx
  int ActivityIdPrefix; // eax
  UINT32 length; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  const unsigned __int16 *v20; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v21[32]; // [rsp+48h] [rbp-28h] BYREF

  v3 = *((_QWORD *)this + 7);
  string = 0;
  length = 0;
  v20 = a2;
  v5 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v3 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v21, &v20);
  v8 = v5(v3, *(_QWORD *)(v6 + 24), &string);
  if ( v8 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    v11 = (unsigned __int16 *)operator new(saturated_mul(++length, 2u));
    v13 = v11;
    if ( v11 )
    {
      v8 = StringCchCopyW(v11, length, StringRawBuffer);
      if ( v8 >= 0 )
      {
        *a3 = v13;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v15);
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
            ActivityIdPrefix,
            (__int64)"StringCchCopy failed!",
            v8);
        }
        operator delete(v13);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v12);
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          35,
          (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
          v14,
          (__int64)"WCHAR[]");
      }
      v8 = -2147024882;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, v7);
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      34,
      (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
      v9,
      (__int64)"m_spJsonObj->GetNamedString failed!",
      v8);
  }
  WindowsDeleteString(string);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800133f0  mov     [rsp-18h+arg_18], rbx
0x1800133f5  push    rbp
0x1800133f6  push    rsi
0x1800133f7  push    rdi
0x1800133f8  mov     rbp, rsp
0x1800133fb  sub     rsp, 70h
0x1800133ff  mov     rax, cs:__security_cookie
0x180013406  xor     rax, rsp
0x180013409  mov     [rbp+var_8], rax
0x18001340d  mov     rdi, [rcx+38h]
0x180013411  mov     rsi, r8
0x180013414  mov     [rbp+string], 0
0x18001341c  xor     ecx, ecx; string
0x18001341e  mov     [rbp+length], 0
0x180013425  mov     [rbp+var_30], rdx
0x180013429  mov     rax, [rdi]
0x18001342c  mov     rbx, [rax+50h]
0x180013430  call    cs:__imp_WindowsDeleteString
0x180013436  lea     rdx, [rbp+var_30]
0x18001343a  mov     [rbp+string], 0
0x180013442  lea     rcx, [rbp+var_28]
0x180013446  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001344b  lea     r8, [rbp+string]
0x18001344f  mov     rcx, rdi
0x180013452  mov     rdx, [rax+18h]
0x180013456  mov     rax, rbx
0x180013459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001345e  mov     ebx, eax
0x180013460  test    eax, eax
0x180013462  jns     short loc_1800134C8
0x180013464  mov     rax, cs:WPP_GLOBAL_Control
0x18001346b  lea     rcx, WPP_GLOBAL_Control
0x180013472  cmp     rax, rcx
0x180013475  jz      loc_1800135CE
0x18001347b  test    byte ptr [rax+1Ch], 8
0x18001347f  jz      loc_1800135CE
0x180013485  cmp     byte ptr [rax+19h], 2
0x180013489  jb      loc_1800135CE
0x18001348f  call    RdpX_GetActivityIdPrefix
0x180013494  lea     rcx, aMSpjsonobjGetn; "m_spJsonObj->GetNamedString failed!"
0x18001349b  mov     [rsp+70h+var_48], ebx
0x18001349f  mov     [rsp+70h+var_50], rcx
0x1800134a4  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x1800134ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800134b2  mov     edx, 22h ; '"'
0x1800134b7  mov     r9d, eax
0x1800134ba  mov     rcx, [rcx+10h]
0x1800134be  call    WPP_SF_DsD
0x1800134c3  jmp     loc_1800135CE
0x1800134c8  mov     rcx, [rbp+string]; string
0x1800134cc  lea     rdx, [rbp+length]; length
0x1800134d0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800134d6  mov     ecx, [rbp+length]
0x1800134d9  mov     rbx, rax
0x1800134dc  inc     ecx
0x1800134de  mov     eax, 2
0x1800134e3  mov     edx, ecx
0x1800134e5  mov     [rbp+length], ecx
0x1800134e8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800134ef  mul     rdx
0x1800134f2  cmovb   rax, rcx
0x1800134f6  mov     rcx, rax; Size
0x1800134f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800134fe  mov     rdi, rax
0x180013501  test    rax, rax
0x180013504  jnz     short loc_18001355A
0x180013506  mov     rax, cs:WPP_GLOBAL_Control
0x18001350d  lea     rcx, WPP_GLOBAL_Control
0x180013514  cmp     rax, rcx
0x180013517  jz      short loc_180013553
0x180013519  test    byte ptr [rax+1Ch], 8
0x18001351d  jz      short loc_180013553
0x18001351f  cmp     byte ptr [rax+19h], 2
0x180013523  jb      short loc_180013553
0x180013525  call    RdpX_GetActivityIdPrefix
0x18001352a  lea     rcx, aWchar; "WCHAR[]"
0x180013531  mov     r9d, eax
0x180013534  mov     [rsp+70h+var_50], rcx
0x180013539  lea     edx, [rdi+23h]
0x18001353c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013543  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x18001354a  mov     rcx, [rcx+10h]
0x18001354e  call    WPP_SF_Ds
0x180013553  mov     ebx, 8007000Eh
0x180013558  jmp     short loc_1800135CE
0x18001355a  mov     edx, [rbp+length]; unsigned __int64
0x18001355d  mov     r8, rbx; unsigned __int16 *
0x180013560  mov     rcx, rdi; unsigned __int16 *
0x180013563  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013568  mov     ebx, eax
0x18001356a  test    eax, eax
0x18001356c  jns     short loc_1800135CB
0x18001356e  mov     rax, cs:WPP_GLOBAL_Control
0x180013575  lea     rcx, WPP_GLOBAL_Control
0x18001357c  cmp     rax, rcx
0x18001357f  jz      short loc_1800135C1
0x180013581  test    byte ptr [rax+1Ch], 8
0x180013585  jz      short loc_1800135C1
0x180013587  cmp     byte ptr [rax+19h], 2
0x18001358b  jb      short loc_1800135C1
0x18001358d  call    RdpX_GetActivityIdPrefix
0x180013592  lea     rcx, aStringcchcopyF; "StringCchCopy failed!"
0x180013599  mov     [rsp+70h+var_48], ebx
0x18001359d  mov     [rsp+70h+var_50], rcx
0x1800135a2  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x1800135a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800135b0  mov     edx, 24h ; '$'
0x1800135b5  mov     r9d, eax
0x1800135b8  mov     rcx, [rcx+10h]
0x1800135bc  call    WPP_SF_DsD
0x1800135c1  mov     rcx, rdi; Block
0x1800135c4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800135c9  jmp     short loc_1800135CE
0x1800135cb  mov     [rsi], rdi
0x1800135ce  mov     rcx, [rbp+string]; string
0x1800135d2  call    cs:__imp_WindowsDeleteString
0x1800135d8  mov     eax, ebx
0x1800135da  mov     rcx, [rbp+var_8]
0x1800135de  xor     rcx, rsp; StackCookie
0x1800135e1  call    __security_check_cookie
0x1800135e6  mov     rbx, [rsp+70h+arg_18]
0x1800135ee  add     rsp, 70h
0x1800135f2  pop     rdi
0x1800135f3  pop     rsi
0x1800135f4  pop     rbp
0x1800135f5  retn
```
