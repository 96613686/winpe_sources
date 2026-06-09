# CRADCApiWorkspace::get_ID(ushort * *)

- ea: `0x180072260`
- end: `0x180072455`
- name: `?get_ID@CRADCApiWorkspace@@UEAAJPEAPEAG@Z`
- size: `501`
- prototype: `__int64 __fastcall(CRADCApiWorkspace *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000b1d8`
- `0x18000ec94`
- `0x18000ece0`
- `0x180072260`
- `0x18009a520`

## import_xrefs

- `ole32!StringFromIID` at `0x180072357`
- `ole32!StringFromIID` at `0x180072357`
- `ole32!CoTaskMemFree` at `0x180072435`
- `ole32!CoTaskMemFree` at `0x180072435`
- `OLEAUT32!__imp_SysAllocString` at `0x1800723c9`
- `OLEAUT32!__imp_SysAllocString` at `0x1800723c9`

## pseudocode

```c
__int64 __fastcall CRADCApiWorkspace::get_ID(CRADCApiWorkspace *this, unsigned __int16 **a2)
{
  IID *v2; // rax
  unsigned int v4; // eax
  HRESULT v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned __int16 *v8; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  LPOLESTR lpsz; // [rsp+30h] [rbp-28h] BYREF
  IID rclsid; // [rsp+38h] [rbp-20h] BYREF

  v2 = (IID *)*((_QWORD *)this + 8);
  lpsz = 0;
  rclsid = 0;
  if ( v2 )
  {
    if ( a2 )
    {
      rclsid = v2[3];
      v5 = StringFromIID(&rclsid, &lpsz);
      if ( v5 >= 0 )
      {
        v8 = SysAllocString(lpsz);
        *a2 = v8;
        if ( v8 )
        {
          v5 = 0;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              WPP_7879eade558e3f84b0af04bcec9e8250_Traceguids,
              CurrentThreadActivityIdPrefix,
              -2147024882);
          }
          v5 = -2147024882;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_7879eade558e3f84b0af04bcec9e8250_Traceguids,
          v7,
          (__int64)"StringFromIID failed",
          v5);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          19,
          WPP_7879eade558e3f84b0af04bcec9e8250_Traceguids,
          v6,
          -2147024809);
      }
      v5 = -2147024809;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_7879eade558e3f84b0af04bcec9e8250_Traceguids,
        v4,
        -2147220971);
    }
    v5 = -2147220971;
  }
  if ( lpsz )
    CoTaskMemFree(lpsz);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180072260  mov     [rsp+arg_10], rbx
0x180072265  push    rdi
0x180072266  sub     rsp, 50h
0x18007226a  mov     rax, cs:__security_cookie
0x180072271  xor     rax, rsp
0x180072274  mov     [rsp+58h+var_10], rax
0x180072279  mov     rax, [rcx+40h]
0x18007227d  xorps   xmm0, xmm0
0x180072280  mov     [rsp+58h+lpsz], 0
0x180072289  mov     rdi, rdx
0x18007228c  movups  xmmword ptr [rsp+58h+rclsid.Data1], xmm0
0x180072291  test    rax, rax
0x180072294  jnz     short loc_1800722EB
0x180072296  mov     rcx, cs:WPP_GLOBAL_Control
0x18007229d  lea     rax, WPP_GLOBAL_Control
0x1800722a4  cmp     rcx, rax
0x1800722a7  jz      short loc_1800722E1
0x1800722a9  test    byte ptr [rcx+1Ch], 8
0x1800722ad  jz      short loc_1800722E1
0x1800722af  cmp     byte ptr [rcx+19h], 2
0x1800722b3  jb      short loc_1800722E1
0x1800722b5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800722ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800722c1  lea     r8, WPP_7879eade558e3f84b0af04bcec9e8250_Traceguids
0x1800722c8  mov     edx, 12h
0x1800722cd  mov     dword ptr [rsp+58h+var_38], 80040215h
0x1800722d5  mov     r9d, eax
0x1800722d8  mov     rcx, [rcx+10h]
0x1800722dc  call    WPP_SF_Dd
0x1800722e1  mov     ebx, 80040215h
0x1800722e6  jmp     loc_18007242B
0x1800722eb  test    rdi, rdi
0x1800722ee  jnz     short loc_180072343
0x1800722f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800722f7  lea     rax, WPP_GLOBAL_Control
0x1800722fe  cmp     rcx, rax
0x180072301  jz      short loc_180072339
0x180072303  test    byte ptr [rcx+1Ch], 8
0x180072307  jz      short loc_180072339
0x180072309  cmp     byte ptr [rcx+19h], 2
0x18007230d  jb      short loc_180072339
0x18007230f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180072314  mov     rcx, cs:WPP_GLOBAL_Control
0x18007231b  lea     edx, [rdi+13h]
0x18007231e  mov     r9d, eax
0x180072321  mov     dword ptr [rsp+58h+var_38], 80070057h
0x180072329  lea     r8, WPP_7879eade558e3f84b0af04bcec9e8250_Traceguids
0x180072330  mov     rcx, [rcx+10h]
0x180072334  call    WPP_SF_Dd
0x180072339  mov     ebx, 80070057h
0x18007233e  jmp     loc_18007242B
0x180072343  movups  xmm0, xmmword ptr [rax+30h]
0x180072347  lea     rdx, [rsp+58h+lpsz]; lplpsz
0x18007234c  lea     rcx, [rsp+58h+rclsid]; rclsid
0x180072351  movdqu  xmmword ptr [rsp+58h+rclsid.Data1], xmm0
0x180072357  call    cs:__imp_StringFromIID
0x18007235d  mov     ebx, eax
0x18007235f  test    eax, eax
0x180072361  jns     short loc_1800723C4
0x180072363  mov     rcx, cs:WPP_GLOBAL_Control
0x18007236a  lea     rax, WPP_GLOBAL_Control
0x180072371  cmp     rcx, rax
0x180072374  jz      loc_18007242B
0x18007237a  test    byte ptr [rcx+1Ch], 8
0x18007237e  jz      loc_18007242B
0x180072384  cmp     byte ptr [rcx+19h], 2
0x180072388  jb      loc_18007242B
0x18007238e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180072393  lea     rcx, aStringfromiidF; "StringFromIID failed"
0x18007239a  mov     [rsp+58h+var_30], ebx
0x18007239e  mov     [rsp+58h+var_38], rcx
0x1800723a3  lea     r8, WPP_7879eade558e3f84b0af04bcec9e8250_Traceguids
0x1800723aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800723b1  mov     edx, 14h
0x1800723b6  mov     r9d, eax
0x1800723b9  mov     rcx, [rcx+10h]
0x1800723bd  call    WPP_SF_DsD
0x1800723c2  jmp     short loc_18007242B
0x1800723c4  mov     rcx, [rsp+58h+lpsz]; psz
0x1800723c9  call    cs:__imp_SysAllocString
0x1800723cf  mov     [rdi], rax
0x1800723d2  test    rax, rax
0x1800723d5  jnz     short loc_180072429
0x1800723d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800723de  lea     rax, WPP_GLOBAL_Control
0x1800723e5  cmp     rcx, rax
0x1800723e8  jz      short loc_180072422
0x1800723ea  test    byte ptr [rcx+1Ch], 8
0x1800723ee  jz      short loc_180072422
0x1800723f0  cmp     byte ptr [rcx+19h], 2
0x1800723f4  jb      short loc_180072422
0x1800723f6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800723fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180072402  lea     r8, WPP_7879eade558e3f84b0af04bcec9e8250_Traceguids
0x180072409  mov     edx, 15h
0x18007240e  mov     dword ptr [rsp+58h+var_38], 8007000Eh
0x180072416  mov     r9d, eax
0x180072419  mov     rcx, [rcx+10h]
0x18007241d  call    WPP_SF_Dd
0x180072422  mov     ebx, 8007000Eh
0x180072427  jmp     short loc_18007242B
0x180072429  xor     ebx, ebx
0x18007242b  mov     rcx, [rsp+58h+lpsz]; pv
0x180072430  test    rcx, rcx
0x180072433  jz      short loc_18007243B
0x180072435  call    cs:__imp_CoTaskMemFree
0x18007243b  mov     eax, ebx
0x18007243d  mov     rcx, [rsp+58h+var_10]
0x180072442  xor     rcx, rsp; StackCookie
0x180072445  call    __security_check_cookie
0x18007244a  mov     rbx, [rsp+58h+arg_10]
0x18007244f  add     rsp, 50h
0x180072453  pop     rdi
0x180072454  retn
```
