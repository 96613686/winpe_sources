# CVdsVolume::OpenHandle(ulong,void * *,_VDS_VOLUME_PROP *)

- ea: `0x140009990`
- end: `0x140009ca5`
- name: `?OpenHandle@CVdsVolume@@QEAAJKPEAPEAXPEAU_VDS_VOLUME_PROP@@@Z`
- size: `789`
- prototype: `__int64 __fastcall(CVdsVolume *__hidden this, unsigned int, void **, struct _VDS_VOLUME_PROP *)`
- caller_count: `8`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140004a80`
- `0x140010b40`
- `0x140011aa0`
- `0x14001f450`
- `0x140040e30`
- `0x140041b50`
- `0x140042230`
- `0x140042c50`

## callees

- `0x140009990`
- `0x140013298`
- `0x1400427c4`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009aa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009b73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009bb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009c38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009c6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009aa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009b73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009bb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009c38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140009c6a`
- `vdsutil!OpenDevice` at `0x140009bfa`
- `vdsutil!OpenDevice` at `0x140009bfa`
- `vdsutil!VdsTraceEx` at `0x140009a3e`
- `vdsutil!VdsTraceEx` at `0x140009a78`
- `vdsutil!VdsTraceEx` at `0x140009a9a`
- `vdsutil!VdsTraceEx` at `0x140009afb`
- `vdsutil!VdsTraceEx` at `0x140009b23`
- `vdsutil!VdsTraceEx` at `0x140009b92`
- `vdsutil!VdsTraceEx` at `0x140009bd6`
- `vdsutil!VdsTraceEx` at `0x140009c29`
- `vdsutil!VdsTraceEx` at `0x140009a3e`
- `vdsutil!VdsTraceEx` at `0x140009a78`
- `vdsutil!VdsTraceEx` at `0x140009a9a`
- `vdsutil!VdsTraceEx` at `0x140009afb`
- `vdsutil!VdsTraceEx` at `0x140009b23`
- `vdsutil!VdsTraceEx` at `0x140009b92`
- `vdsutil!VdsTraceEx` at `0x140009bd6`
- `vdsutil!VdsTraceEx` at `0x140009c29`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400099e5`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x1400099e5`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140009a4a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140009abc`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140009b07`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140009b52`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140009b9e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140009be2`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140009c79`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140009a4a`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140009abc`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140009b07`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140009b52`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140009b9e`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140009be2`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140009c79`

## string_xrefs

- `0x140009a32`: `CVdsVolume::OpenHandle, 1, hr=%lX`
- `0x1400099d4`: `CVdsVolume::OpenHandle()`
- `0x140009a6c`: `CVdsVolume::OpenHandle, 1.3, volume=(%S)`
- `0x140009a8c`: `CVdsVolume::OpenHandle, 1.5, hr=%lX`
- `0x140009af4`: `CVdsVolume::OpenHandle, 1.7, hr=%lX`
- `0x140009b1c`: `CVdsVolume::OpenHandle, 2`
- `0x140009b62`: `CVdsVolume::OpenHandle, 3, hr=%lX`
- `0x140009b81`: `CVdsVolume::OpenHandle, 3.3, NO MEDIA`
- `0x140009bc5`: `CVdsVolume::OpenHandle, 3.6, VOLUME_OFFLINE`
- `0x140009c18`: `CVdsVolume::OpenHandle, 4, volume=(%S), error=%ld`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVdsVolume::OpenHandle(CVdsVolume *this, __int64 a2, void **a3, struct _VDS_VOLUME_PROP *a4)
{
  struct _VDS_VOLUME_PROP *v7; // rdi
  signed int IsPackOffline; // ebx
  const wchar_t *v10; // r15
  const wchar_t *pwszName; // r9
  VDS_VOLUME_STATUS status; // eax
  LPWSTR v13; // rcx
  LPWSTR v14; // rcx
  LPWSTR v15; // rcx
  LPWSTR v16; // rcx
  _BYTE v17[16]; // [rsp+30h] [rbp-78h] BYREF
  __int128 v18; // [rsp+40h] [rbp-68h] BYREF
  __int128 v19; // [rsp+50h] [rbp-58h]
  __int128 v20; // [rsp+60h] [rbp-48h]
  __int64 v21; // [rsp+70h] [rbp-38h]

  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v17, 0x5Eu, "CVdsVolume::OpenHandle()");
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v7 = (struct _VDS_VOLUME_PROP *)&v18;
  if ( a4 )
    v7 = a4;
  IsPackOffline = (*(__int64 (__fastcall **)(_QWORD, struct _VDS_VOLUME_PROP *))(**((_QWORD **)this + 16) + 24LL))(
                    *((_QWORD *)this + 16),
                    v7);
  if ( IsPackOffline < 0 )
  {
    VdsTraceEx(94, 0, "CVdsVolume::OpenHandle, 1, hr=%lX", (unsigned int)IsPackOffline);
LABEL_5:
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
    return (unsigned int)IsPackOffline;
  }
  v10 = L"UNKNOWN";
  pwszName = L"UNKNOWN";
  if ( v7->pwszName )
    pwszName = v7->pwszName;
  VdsTraceEx(94, 3, "CVdsVolume::OpenHandle, 1.3, volume=(%S)", pwszName);
  status = v7->status;
  if ( status == VDS_VS_FAILED )
  {
    VdsTraceEx(94, 0, "CVdsVolume::OpenHandle, 1.5, hr=%lX", -2147212239);
    v13 = v7->pwszName;
    if ( v13 )
    {
      CoTaskMemFree(v13);
      v7->pwszName = 0;
    }
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
    return 2147755057LL;
  }
  else
  {
    v14 = v7->pwszName;
    if ( v14 )
    {
      if ( status == VDS_VS_NO_MEDIA )
      {
        CoTaskMemFree(v14);
        v7->pwszName = 0;
        VdsTraceEx(94, 3, "CVdsVolume::OpenHandle, 3.3, NO MEDIA");
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
        return 2147755026LL;
      }
      else if ( (v7->ulFlags & 0x40000) != 0 )
      {
        CoTaskMemFree(v14);
        v7->pwszName = 0;
        VdsTraceEx(94, 1, "CVdsVolume::OpenHandle, 3.6, VOLUME_OFFLINE");
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
        return 2147755069LL;
      }
      else
      {
        IsPackOffline = OpenDevice(v14, 0x80000000LL, a3);
        if ( IsPackOffline )
        {
          if ( v7->pwszName )
            v10 = v7->pwszName;
          VdsTraceEx(94, 1, "CVdsVolume::OpenHandle, 4, volume=(%S), error=%ld", v10, IsPackOffline);
          v15 = v7->pwszName;
          if ( v15 )
          {
            CoTaskMemFree(v15);
            v7->pwszName = 0;
          }
          if ( IsPackOffline > 0 )
            IsPackOffline = (unsigned __int16)IsPackOffline | 0x80070000;
          goto LABEL_5;
        }
        if ( !a4 )
        {
          v16 = v7->pwszName;
          if ( v16 )
          {
            CoTaskMemFree(v16);
            v7->pwszName = 0;
          }
        }
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
        return 0;
      }
    }
    else
    {
      IsPackOffline = CVdsVolume::IsPackOffline(this);
      if ( IsPackOffline )
      {
        if ( IsPackOffline != 1 )
        {
          VdsTraceEx(94, 0, "CVdsVolume::OpenHandle, 3, hr=%lX", (unsigned int)IsPackOffline);
          goto LABEL_5;
        }
        VdsTraceEx(94, 0, "CVdsVolume::OpenHandle, 2");
        VdsLogError(0xC2000010, 0, 0, 1u, 0x20A0005u, 0);
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
        return 2147755073LL;
      }
      else
      {
        VdsTraceEx(94, 0, "CVdsVolume::OpenHandle, 1.7, hr=%lX", -2147212220);
        CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v17);
        return 2147755076LL;
      }
    }
  }
}

```

## disassembly

```asm
0x140009990  mov     [rsp+arg_8], rbx
0x140009995  push    rbp
0x140009996  push    rsi
0x140009997  push    rdi
0x140009998  push    r14
0x14000999a  push    r15
0x14000999c  sub     rsp, 80h
0x1400099a3  mov     rax, cs:__security_cookie
0x1400099aa  xor     rax, rsp
0x1400099ad  mov     [rsp+0A8h+var_30], rax
0x1400099b2  mov     rsi, r9
0x1400099b5  mov     r14, r8
0x1400099b8  mov     rbp, rcx
0x1400099bb  xorps   xmm0, xmm0
0x1400099be  xor     eax, eax
0x1400099c0  movups  [rsp+0A8h+var_68], xmm0
0x1400099c5  movups  [rsp+0A8h+var_58], xmm0
0x1400099ca  movups  [rsp+0A8h+var_48], xmm0
0x1400099cf  mov     [rsp+0A8h+var_38], rax
0x1400099d4  lea     r8, aCvdsvolumeOpen_5; "CVdsVolume::OpenHandle()"
0x1400099db  mov     edx, 5Eh ; '^'
0x1400099e0  lea     rcx, [rsp+0A8h+var_78]
0x1400099e5  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x1400099eb  nop
0x1400099ec  xorps   xmm0, xmm0
0x1400099ef  xor     eax, eax
0x1400099f1  movups  [rsp+0A8h+var_68], xmm0
0x1400099f6  movups  [rsp+0A8h+var_58], xmm0
0x1400099fb  movups  [rsp+0A8h+var_48], xmm0
0x140009a00  mov     [rsp+0A8h+var_38], rax
0x140009a05  lea     rdi, [rsp+0A8h+var_68]
0x140009a0a  test    rsi, rsi
0x140009a0d  cmovnz  rdi, rsi
0x140009a11  mov     rcx, [rbp+80h]
0x140009a18  mov     rax, [rcx]
0x140009a1b  mov     rdx, rdi
0x140009a1e  mov     rax, [rax+18h]
0x140009a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a27  mov     ebx, eax
0x140009a29  mov     ecx, 5Eh ; '^'
0x140009a2e  test    eax, eax
0x140009a30  jns     short loc_140009A57
0x140009a32  lea     r8, aCvdsvolumeOpen_3; "CVdsVolume::OpenHandle, 1, hr=%lX"
0x140009a39  xor     edx, edx
0x140009a3b  mov     r9d, ebx
0x140009a3e  call    cs:__imp_VdsTraceEx
0x140009a44  nop
0x140009a45  lea     rcx, [rsp+0A8h+var_78]
0x140009a4a  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140009a50  mov     eax, ebx
0x140009a52  jmp     loc_140009C81
0x140009a57  mov     rax, [rdi+30h]
0x140009a5b  lea     r15, aUnknown_0; "UNKNOWN"
0x140009a62  mov     r9, r15
0x140009a65  test    rax, rax
0x140009a68  cmovnz  r9, rax
0x140009a6c  lea     r8, aCvdsvolumeOpen_2; "CVdsVolume::OpenHandle, 1.3, volume=(%S"...
0x140009a73  mov     edx, 3
0x140009a78  call    cs:__imp_VdsTraceEx
0x140009a7e  mov     eax, [rdi+14h]
0x140009a81  cmp     eax, 5
0x140009a84  jnz     short loc_140009ACC
0x140009a86  mov     r9d, 80042431h
0x140009a8c  lea     r8, aCvdsvolumeOpen_6; "CVdsVolume::OpenHandle, 1.5, hr=%lX"
0x140009a93  xor     edx, edx
0x140009a95  mov     ecx, 5Eh ; '^'
0x140009a9a  call    cs:__imp_VdsTraceEx
0x140009aa0  mov     rcx, [rdi+30h]; pv
0x140009aa4  test    rcx, rcx
0x140009aa7  jz      short loc_140009AB7
0x140009aa9  call    cs:__imp_CoTaskMemFree
0x140009aaf  mov     qword ptr [rdi+30h], 0
0x140009ab7  lea     rcx, [rsp+0A8h+var_78]
0x140009abc  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140009ac2  mov     eax, 80042431h
0x140009ac7  jmp     loc_140009C81
0x140009acc  mov     rcx, [rdi+30h]; pv
0x140009ad0  test    rcx, rcx
0x140009ad3  jnz     loc_140009B6E
0x140009ad9  mov     rcx, rbp; this
0x140009adc  call    ?IsPackOffline@CVdsVolume@@AEAAJXZ; CVdsVolume::IsPackOffline(void)
0x140009ae1  mov     ebx, eax
0x140009ae3  xor     edx, edx
0x140009ae5  mov     ecx, 5Eh ; '^'
0x140009aea  test    eax, eax
0x140009aec  jnz     short loc_140009B17
0x140009aee  mov     r9d, 80042444h
0x140009af4  lea     r8, aCvdsvolumeOpen; "CVdsVolume::OpenHandle, 1.7, hr=%lX"
0x140009afb  call    cs:__imp_VdsTraceEx
0x140009b01  nop
0x140009b02  lea     rcx, [rsp+0A8h+var_78]
0x140009b07  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140009b0d  mov     eax, 80042444h
0x140009b12  jmp     loc_140009C81
0x140009b17  cmp     ebx, 1
0x140009b1a  jnz     short loc_140009B62
0x140009b1c  lea     r8, aCvdsvolumeOpen_1; "CVdsVolume::OpenHandle, 2"
0x140009b23  call    cs:__imp_VdsTraceEx
0x140009b29  mov     [rsp+0A8h+var_80], 0; unsigned __int16 *
0x140009b32  mov     [rsp+0A8h+var_88], 20A0005h; unsigned int
0x140009b3a  mov     r9d, ebx; unsigned int
0x140009b3d  xor     r8d, r8d; void *
0x140009b40  xor     edx, edx; unsigned int
0x140009b42  mov     ecx, 0C2000010h; unsigned int
0x140009b47  call    ?VdsLogError@@YAXKKPEAXKKPEAGZZ; VdsLogError(ulong,ulong,void *,ulong,ulong,ushort *,...)
0x140009b4c  nop
0x140009b4d  lea     rcx, [rsp+0A8h+var_78]
0x140009b52  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140009b58  mov     eax, 80042441h
0x140009b5d  jmp     loc_140009C81
0x140009b62  lea     r8, aCvdsvolumeOpen_4; "CVdsVolume::OpenHandle, 3, hr=%lX"
0x140009b69  jmp     loc_140009A3B
0x140009b6e  cmp     eax, 3
0x140009b71  jnz     short loc_140009BAE
0x140009b73  call    cs:__imp_CoTaskMemFree
0x140009b79  mov     qword ptr [rdi+30h], 0
0x140009b81  lea     r8, aCvdsvolumeOpen_0; "CVdsVolume::OpenHandle, 3.3, NO MEDIA"
0x140009b88  mov     edx, 3
0x140009b8d  mov     ecx, 5Eh ; '^'
0x140009b92  call    cs:__imp_VdsTraceEx
0x140009b98  nop
0x140009b99  lea     rcx, [rsp+0A8h+var_78]
0x140009b9e  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140009ba4  mov     eax, 80042412h
0x140009ba9  jmp     loc_140009C81
0x140009bae  test    dword ptr [rdi+28h], 40000h
0x140009bb5  jz      short loc_140009BF2
0x140009bb7  call    cs:__imp_CoTaskMemFree
0x140009bbd  mov     qword ptr [rdi+30h], 0
0x140009bc5  lea     r8, aCvdsvolumeOpen_7; "CVdsVolume::OpenHandle, 3.6, VOLUME_OFF"...
0x140009bcc  mov     edx, 1
0x140009bd1  mov     ecx, 5Eh ; '^'
0x140009bd6  call    cs:__imp_VdsTraceEx
0x140009bdc  nop
0x140009bdd  lea     rcx, [rsp+0A8h+var_78]
0x140009be2  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140009be8  mov     eax, 8004243Dh
0x140009bed  jmp     loc_140009C81
0x140009bf2  mov     r8, r14
0x140009bf5  mov     edx, 80000000h
0x140009bfa  call    cs:__imp_OpenDevice
0x140009c00  mov     ebx, eax
0x140009c02  test    eax, eax
0x140009c04  jz      short loc_140009C5C
0x140009c06  mov     rax, [rdi+30h]
0x140009c0a  test    rax, rax
0x140009c0d  cmovnz  r15, rax
0x140009c11  mov     [rsp+0A8h+var_88], ebx
0x140009c15  mov     r9, r15
0x140009c18  lea     r8, aCvdsvolumeOpen_8; "CVdsVolume::OpenHandle, 4, volume=(%S),"...
0x140009c1f  mov     edx, 1
0x140009c24  mov     ecx, 5Eh ; '^'
0x140009c29  call    cs:__imp_VdsTraceEx
0x140009c2f  mov     rcx, [rdi+30h]; pv
0x140009c33  test    rcx, rcx
0x140009c36  jz      short loc_140009C46
0x140009c38  call    cs:__imp_CoTaskMemFree
0x140009c3e  mov     qword ptr [rdi+30h], 0
0x140009c46  test    ebx, ebx
0x140009c48  jle     loc_140009A45
0x140009c4e  movzx   ebx, bx
0x140009c51  or      ebx, 80070000h
0x140009c57  jmp     loc_140009A45
0x140009c5c  test    rsi, rsi
0x140009c5f  jnz     short loc_140009C74
0x140009c61  mov     rcx, [rdi+30h]; pv
0x140009c65  test    rcx, rcx
0x140009c68  jz      short loc_140009C74
0x140009c6a  call    cs:__imp_CoTaskMemFree
0x140009c70  mov     [rdi+30h], rsi
0x140009c74  lea     rcx, [rsp+0A8h+var_78]
0x140009c79  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140009c7f  xor     eax, eax
0x140009c81  mov     rcx, [rsp+0A8h+var_30]
0x140009c86  xor     rcx, rsp; StackCookie
0x140009c89  call    __security_check_cookie
0x140009c8e  mov     rbx, [rsp+0A8h+arg_8]
0x140009c96  add     rsp, 80h
0x140009c9d  pop     r15
0x140009c9f  pop     r14
0x140009ca1  pop     rdi
0x140009ca2  pop     rsi
0x140009ca3  pop     rbp
0x140009ca4  retn
```
