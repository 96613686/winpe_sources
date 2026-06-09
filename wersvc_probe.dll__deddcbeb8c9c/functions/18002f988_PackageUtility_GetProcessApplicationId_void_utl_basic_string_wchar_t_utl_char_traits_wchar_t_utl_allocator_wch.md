# PackageUtility::GetProcessApplicationId(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x18002f988`
- end: `0x18002fbaa`
- name: `?GetProcessApplicationId@PackageUtility@@SAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `546`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800298fc`

## callees

- `0x1800029d0`
- `0x180004458`
- `0x18000458c`
- `0x180006a80`
- `0x180011648`
- `0x180011ef8`
- `0x18002f988`
- `0x180033ea8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fb7f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002fb7f`
- `ext-ms-win-wer-xbox-l1-1-2!XerGetPackageIdentity` at `0x18002faba`
- `ext-ms-win-wer-xbox-l1-1-2!XerGetPackageIdentity` at `0x18002faba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PackageUtility::GetProcessApplicationId(HANDLE ProcessHandle, __int64 a2)
{
  void *v4; // rdi
  unsigned __int16 **v5; // r8
  int ProcessAppId; // eax
  int PackageIdentity; // ebx
  __int64 v8; // r8
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  int v12; // [rsp+30h] [rbp-148h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-140h] BYREF
  _BYTE v14[272]; // [rsp+40h] [rbp-138h] BYREF

  v4 = 0;
  v12 = 0;
  if ( !ProcessHandle || !a2 )
  {
    PackageIdentity = -2147024809;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_31;
    v10 = 15;
    goto LABEL_30;
  }
  if ( (unsigned __int8)IsGetPackageFullNamePresent() )
  {
    pv = 0;
    ProcessAppId = CallerIdentity::GetProcessAppId(ProcessHandle, &pv, v5);
    PackageIdentity = ProcessAppId;
    if ( ProcessAppId < 0 )
    {
      if ( ProcessAppId != -2147023728
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          &WPP_426532d07a9735b83ad974c5a485a15d_Traceguids,
          (unsigned int)ProcessAppId);
      }
      v4 = pv;
      goto LABEL_31;
    }
    v4 = pv;
    if ( pv )
    {
      v8 = -1;
      do
        ++v8;
      while ( *((_WORD *)pv + v8) );
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a2, pv) )
    {
      PackageIdentity = -2147024882;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_31;
      v10 = 17;
      goto LABEL_30;
    }
LABEL_26:
    PackageIdentity = 0;
    goto LABEL_31;
  }
  if ( !(unsigned __int8)IsXerGetPackageIdentityPresent() )
    goto LABEL_26;
  v12 = 131;
  PackageIdentity = XerGetPackageIdentity(ProcessHandle, 0, 0, &v12, v14);
  if ( PackageIdentity >= 0 )
  {
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a2, v14) )
      goto LABEL_26;
    PackageIdentity = -2147024882;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_31;
    v10 = 19;
LABEL_30:
    WPP_SF_(v9[2], v10, &WPP_426532d07a9735b83ad974c5a485a15d_Traceguids);
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      &WPP_426532d07a9735b83ad974c5a485a15d_Traceguids,
      (unsigned int)PackageIdentity);
LABEL_31:
  if ( v4 )
    CoTaskMemFree(v4);
  return (unsigned int)PackageIdentity;
}

```

## disassembly

```asm
0x18002f988  mov     [rsp+arg_10], rbx
0x18002f98d  push    rbp
0x18002f98e  push    rsi
0x18002f98f  push    rdi
0x18002f990  sub     rsp, 160h
0x18002f997  mov     rax, cs:__security_cookie
0x18002f99e  xor     rax, rsp
0x18002f9a1  mov     [rsp+178h+var_28], rax
0x18002f9a9  mov     rsi, rdx
0x18002f9ac  mov     rbx, rcx
0x18002f9af  xor     ebp, ebp
0x18002f9b1  mov     edi, ebp
0x18002f9b3  mov     [rsp+178h+var_148], ebp
0x18002f9b7  test    rcx, rcx
0x18002f9ba  jz      loc_18002FB43
0x18002f9c0  test    rdx, rdx
0x18002f9c3  jz      loc_18002FB43
0x18002f9c9  call    IsGetPackageFullNamePresent
0x18002f9ce  test    al, al
0x18002f9d0  jz      loc_18002FA8E
0x18002f9d6  mov     [rsp+178h+pv], rbp
0x18002f9db  lea     rdx, [rsp+178h+pv]; void *
0x18002f9e0  mov     rcx, rbx; ProcessHandle
0x18002f9e3  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x18002f9e8  mov     ebx, eax
0x18002f9ea  test    eax, eax
0x18002f9ec  jns     short loc_18002FA2E
0x18002f9ee  cmp     eax, 80070490h
0x18002f9f3  jz      short loc_18002FA24
0x18002f9f5  lea     rax, WPP_GLOBAL_Control
0x18002f9fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa03  cmp     rcx, rax
0x18002fa06  jz      short loc_18002FA24
0x18002fa08  test    byte ptr [rcx+1Ch], 1
0x18002fa0c  jz      short loc_18002FA24
0x18002fa0e  lea     edx, [rbp+10h]
0x18002fa11  mov     r9d, ebx
0x18002fa14  lea     r8, WPP_426532d07a9735b83ad974c5a485a15d_Traceguids
0x18002fa1b  mov     rcx, [rcx+10h]
0x18002fa1f  call    WPP_SF_d
0x18002fa24  mov     rdi, [rsp+178h+pv]
0x18002fa29  jmp     loc_18002FB77
0x18002fa2e  mov     rdi, [rsp+178h+pv]
0x18002fa33  test    rdi, rdi
0x18002fa36  jz      short loc_18002FA48
0x18002fa38  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002fa3c  inc     r8
0x18002fa3f  cmp     [rdi+r8*2], bp
0x18002fa44  jnz     short loc_18002FA3C
0x18002fa46  jmp     short loc_18002FA4B
0x18002fa48  mov     r8, rbp
0x18002fa4b  mov     rdx, rdi
0x18002fa4e  mov     rcx, rsi
0x18002fa51  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18002fa56  test    al, al
0x18002fa58  jnz     loc_18002FB3F
0x18002fa5e  mov     ebx, 8007000Eh
0x18002fa63  lea     rax, WPP_GLOBAL_Control
0x18002fa6a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fa71  cmp     rcx, rax
0x18002fa74  jz      loc_18002FB77
0x18002fa7a  test    byte ptr [rcx+1Ch], 1
0x18002fa7e  jz      loc_18002FB77
0x18002fa84  mov     edx, 11h
0x18002fa89  jmp     loc_18002FB66
0x18002fa8e  call    IsXerGetPackageIdentityPresent
0x18002fa93  test    al, al
0x18002fa95  jz      loc_18002FB3F
0x18002fa9b  mov     [rsp+178h+var_148], 83h
0x18002faa3  lea     rax, [rsp+178h+var_138]
0x18002faa8  mov     [rsp+178h+var_158], rax
0x18002faad  lea     r9, [rsp+178h+var_148]
0x18002fab2  xor     r8d, r8d
0x18002fab5  xor     edx, edx
0x18002fab7  mov     rcx, rbx
0x18002faba  call    cs:__imp_XerGetPackageIdentity
0x18002fac0  mov     ebx, eax
0x18002fac2  test    eax, eax
0x18002fac4  jns     short loc_18002FB01
0x18002fac6  lea     rax, WPP_GLOBAL_Control
0x18002facd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fad4  cmp     rcx, rax
0x18002fad7  jz      loc_18002FB77
0x18002fadd  test    byte ptr [rcx+1Ch], 1
0x18002fae1  jz      loc_18002FB77
0x18002fae7  mov     edx, 12h
0x18002faec  mov     r9d, ebx
0x18002faef  lea     r8, WPP_426532d07a9735b83ad974c5a485a15d_Traceguids
0x18002faf6  mov     rcx, [rcx+10h]
0x18002fafa  call    WPP_SF_d
0x18002faff  jmp     short loc_18002FB77
0x18002fb01  mov     r8d, [rsp+178h+var_148]
0x18002fb06  dec     r8d
0x18002fb09  lea     rdx, [rsp+178h+var_138]
0x18002fb0e  mov     rcx, rsi
0x18002fb11  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18002fb16  test    al, al
0x18002fb18  jnz     short loc_18002FB3F
0x18002fb1a  mov     ebx, 8007000Eh
0x18002fb1f  lea     rax, WPP_GLOBAL_Control
0x18002fb26  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb2d  cmp     rcx, rax
0x18002fb30  jz      short loc_18002FB77
0x18002fb32  test    byte ptr [rcx+1Ch], 1
0x18002fb36  jz      short loc_18002FB77
0x18002fb38  mov     edx, 13h
0x18002fb3d  jmp     short loc_18002FB66
0x18002fb3f  mov     ebx, ebp
0x18002fb41  jmp     short loc_18002FB77
0x18002fb43  mov     ebx, 80070057h
0x18002fb48  lea     rax, WPP_GLOBAL_Control
0x18002fb4f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fb56  cmp     rcx, rax
0x18002fb59  jz      short loc_18002FB77
0x18002fb5b  test    byte ptr [rcx+1Ch], 1
0x18002fb5f  jz      short loc_18002FB77
0x18002fb61  mov     edx, 0Fh
0x18002fb66  lea     r8, WPP_426532d07a9735b83ad974c5a485a15d_Traceguids
0x18002fb6d  mov     rcx, [rcx+10h]
0x18002fb71  call    WPP_SF_
0x18002fb76  nop
0x18002fb77  test    rdi, rdi
0x18002fb7a  jz      short loc_18002FB85
0x18002fb7c  mov     rcx, rdi; pv
0x18002fb7f  call    cs:__imp_CoTaskMemFree
0x18002fb85  mov     eax, ebx
0x18002fb87  mov     rcx, [rsp+178h+var_28]
0x18002fb8f  xor     rcx, rsp; StackCookie
0x18002fb92  call    __security_check_cookie
0x18002fb97  mov     rbx, [rsp+178h+arg_10]
0x18002fb9f  add     rsp, 160h
0x18002fba6  pop     rdi
0x18002fba7  pop     rsi
0x18002fba8  pop     rbp
0x18002fba9  retn
```
