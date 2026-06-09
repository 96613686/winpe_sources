# AppInfoCallback::GetAppList(__MIDL___MIDL_itf_wpnplatform_0000_0035_0002 * *)

- ea: `0x1800ed79c`
- end: `0x1800ed995`
- name: `?GetAppList@AppInfoCallback@@QEAAJPEAPEAU__MIDL___MIDL_itf_wpnplatform_0000_0035_0002@@@Z`
- size: `505`
- prototype: `int(AppInfoCallback *__hidden this, struct __MIDL___MIDL_itf_wpnplatform_0000_0035_0002 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a777c`
- `0x1800b0fa8`

## callees

- `0x18002ee38`
- `0x180062bf0`
- `0x1800af0a4`
- `0x1800ed79c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ed909`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ed91a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ed909`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ed91a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ed835`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ed89f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ed835`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ed89f`

## pseudocode

```c
__int64 __fastcall AppInfoCallback::GetAppList(
        AppInfoCallback *this,
        struct __MIDL___MIDL_itf_wpnplatform_0000_0035_0002 **a2)
{
  __int64 *v2; // r14
  int v5; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  struct __MIDL___MIDL_itf_wpnplatform_0000_0035_0002 *v10; // rdi
  SIZE_T v11; // rcx
  LPVOID v12; // rax
  void *v13; // rcx
  __int64 i; // r8
  __int64 v15; // rdx
  int v16; // eax
  int v18; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  SIZE_T cb; // [rsp+40h] [rbp+8h] BYREF

  v2 = (__int64 *)*((_QWORD *)this + 3);
  cb = 0;
  v5 = ULongLongMult(*((unsigned int *)this + 10), 0x18u, &cb);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v10 = (struct __MIDL___MIDL_itf_wpnplatform_0000_0035_0002 *)CoTaskMemAlloc(0x10u);
    if ( v10 )
    {
      v11 = cb;
      *(_DWORD *)v10 = *((_DWORD *)this + 10);
      *((_QWORD *)v10 + 1) = 0;
      v12 = CoTaskMemAlloc(v11);
      *((_QWORD *)v10 + 1) = v12;
      if ( v12 )
      {
        for ( i = 0; (unsigned int)i < *((_DWORD *)this + 10); v2 = (__int64 *)*v2 )
        {
          v15 = 3 * i;
          i = (unsigned int)(i + 1);
          *(_QWORD *)(*((_QWORD *)v10 + 1) + 8 * v15) = v2[2];
          *(_QWORD *)(*((_QWORD *)v10 + 1) + 8 * v15 + 16) = v2[4];
          v16 = *((_DWORD *)v2 + 6);
          v2[2] = 0;
          v2[4] = 0;
          *(_DWORD *)(*((_QWORD *)v10 + 1) + 8 * v15 + 8) = v16;
          *(_DWORD *)(*((_QWORD *)v10 + 1) + 8 * v15 + 12) = *((_DWORD *)v2 + 7);
        }
        *a2 = v10;
      }
      else
      {
        v6 = -2147024882;
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x796,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
          (const char *)0x8007000ELL,
          v18);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            107,
            WPP_00912b6861fc335f2cbb59491e908f50_Traceguids,
            2147942414LL);
        v13 = (void *)*((_QWORD *)v10 + 1);
        if ( v13 )
        {
          CoTaskMemFree(v13);
          *((_QWORD *)v10 + 1) = 0;
        }
        CoTaskMemFree(v10);
      }
    }
    else
    {
      v6 = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x790,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
        (const char *)0x8007000ELL,
        v18);
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v8 = 106;
        v9 = 2147942414LL;
        goto LABEL_5;
      }
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x78C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\settings\\settingsendpoint.cpp",
      (const char *)(unsigned int)v5,
      v18);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v8 = 105;
      v9 = v6;
LABEL_5:
      WPP_SF_d(v7[2], v8, WPP_00912b6861fc335f2cbb59491e908f50_Traceguids, v9);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800ed79c  mov     rax, rsp
0x1800ed79f  mov     [rax+10h], rbx
0x1800ed7a3  mov     [rax+18h], rsi
0x1800ed7a7  push    rdi
0x1800ed7a8  push    r14
0x1800ed7aa  push    r15; int
0x1800ed7ac  sub     rsp, 20h
0x1800ed7b0  mov     r14, [rcx+18h]
0x1800ed7b4  lea     r8, [rax+8]; unsigned __int64 *
0x1800ed7b8  mov     r15, rdx
0x1800ed7bb  mov     qword ptr [rax+8], 0
0x1800ed7c3  mov     rsi, rcx
0x1800ed7c6  mov     edx, 18h; unsigned __int64
0x1800ed7cb  mov     ecx, [rcx+28h]; unsigned __int64
0x1800ed7ce  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800ed7d3  mov     ebx, eax
0x1800ed7d5  test    eax, eax
0x1800ed7d7  jns     short loc_1800ED830
0x1800ed7d9  mov     rcx, [rsp+38h]; this
0x1800ed7de  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800ed7e5  mov     r9d, eax; char *
0x1800ed7e8  mov     edx, 78Ch; void *
0x1800ed7ed  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ed7f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ed7f9  lea     rax, WPP_GLOBAL_Control
0x1800ed800  cmp     rcx, rax
0x1800ed803  jz      loc_1800ED97F
0x1800ed809  test    byte ptr [rcx+1Ch], 80h
0x1800ed80d  jz      loc_1800ED97F
0x1800ed813  mov     edx, 69h ; 'i'
0x1800ed818  mov     r9d, ebx
0x1800ed81b  mov     rcx, [rcx+10h]
0x1800ed81f  lea     r8, WPP_00912b6861fc335f2cbb59491e908f50_Traceguids
0x1800ed826  call    WPP_SF_d
0x1800ed82b  jmp     loc_1800ED97F
0x1800ed830  mov     ecx, 10h; cb
0x1800ed835  call    cs:__imp_CoTaskMemAlloc
0x1800ed83b  mov     rdi, rax
0x1800ed83e  test    rax, rax
0x1800ed841  jnz     short loc_1800ED88D
0x1800ed843  mov     rcx, [rsp+38h]; this
0x1800ed848  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800ed84f  mov     ebx, 8007000Eh
0x1800ed854  mov     edx, 790h; void *
0x1800ed859  mov     r9d, ebx; char *
0x1800ed85c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ed861  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ed868  lea     rax, WPP_GLOBAL_Control
0x1800ed86f  cmp     rcx, rax
0x1800ed872  jz      loc_1800ED97F
0x1800ed878  test    byte ptr [rcx+1Ch], 80h
0x1800ed87c  jz      loc_1800ED97F
0x1800ed882  lea     edx, [rdi+6Ah]
0x1800ed885  mov     r9d, 8007000Eh
0x1800ed88b  jmp     short loc_1800ED81B
0x1800ed88d  mov     eax, [rsi+28h]
0x1800ed890  mov     rcx, [rsp+38h+cb]; cb
0x1800ed895  mov     [rdi], eax
0x1800ed897  mov     qword ptr [rdi+8], 0
0x1800ed89f  call    cs:__imp_CoTaskMemAlloc
0x1800ed8a5  mov     [rdi+8], rax
0x1800ed8a9  test    rax, rax
0x1800ed8ac  jnz     short loc_1800ED922
0x1800ed8ae  mov     rcx, [rsp+38h]; this
0x1800ed8b3  lea     r8, aOnecoreuapBase_154; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800ed8ba  mov     ebx, 8007000Eh
0x1800ed8bf  mov     edx, 796h; void *
0x1800ed8c4  mov     r9d, ebx; char *
0x1800ed8c7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ed8cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ed8d3  lea     rax, WPP_GLOBAL_Control
0x1800ed8da  cmp     rcx, rax
0x1800ed8dd  jz      short loc_1800ED900
0x1800ed8df  test    byte ptr [rcx+1Ch], 80h
0x1800ed8e3  jz      short loc_1800ED900
0x1800ed8e5  mov     rcx, [rcx+10h]
0x1800ed8e9  lea     r8, WPP_00912b6861fc335f2cbb59491e908f50_Traceguids
0x1800ed8f0  mov     edx, 6Bh ; 'k'
0x1800ed8f5  mov     r9d, 8007000Eh
0x1800ed8fb  call    WPP_SF_d
0x1800ed900  mov     rcx, [rdi+8]; pv
0x1800ed904  test    rcx, rcx
0x1800ed907  jz      short loc_1800ED917
0x1800ed909  call    cs:__imp_CoTaskMemFree
0x1800ed90f  mov     qword ptr [rdi+8], 0
0x1800ed917  mov     rcx, rdi; pv
0x1800ed91a  call    cs:__imp_CoTaskMemFree
0x1800ed920  jmp     short loc_1800ED97F
0x1800ed922  xor     r8d, r8d
0x1800ed925  cmp     [rsi+28h], r8d
0x1800ed929  jbe     short loc_1800ED97C
0x1800ed92b  mov     rcx, [rdi+8]
0x1800ed92f  lea     rdx, [r8+r8*2]
0x1800ed933  mov     rax, [r14+10h]
0x1800ed937  inc     r8d
0x1800ed93a  mov     [rcx+rdx*8], rax
0x1800ed93e  mov     rcx, [rdi+8]
0x1800ed942  mov     rax, [r14+20h]
0x1800ed946  mov     [rcx+rdx*8+10h], rax
0x1800ed94b  mov     eax, [r14+18h]
0x1800ed94f  mov     qword ptr [r14+10h], 0
0x1800ed957  mov     qword ptr [r14+20h], 0
0x1800ed95f  mov     rcx, [rdi+8]
0x1800ed963  mov     [rcx+rdx*8+8], eax
0x1800ed967  mov     eax, [r14+1Ch]
0x1800ed96b  mov     rcx, [rdi+8]
0x1800ed96f  mov     [rcx+rdx*8+0Ch], eax
0x1800ed973  mov     r14, [r14]
0x1800ed976  cmp     r8d, [rsi+28h]
0x1800ed97a  jb      short loc_1800ED92B
0x1800ed97c  mov     [r15], rdi
0x1800ed97f  mov     rsi, [rsp+38h+arg_10]
0x1800ed984  mov     eax, ebx
0x1800ed986  mov     rbx, [rsp+38h+arg_8]
0x1800ed98b  add     rsp, 20h
0x1800ed98f  pop     r15
0x1800ed991  pop     r14
0x1800ed993  pop     rdi
0x1800ed994  retn
```
