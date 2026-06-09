# DigestTelemetry::RecordDirectDigestCall(long,uchar,ulong,ulong,ulong,ulong)

- ea: `0x1800109f8`
- end: `0x180010cfe`
- name: `?RecordDirectDigestCall@DigestTelemetry@@YAXJEKKKK@Z`
- size: `774`
- prototype: `void __fastcall(DigestTelemetry *__hidden this, int, unsigned __int8, unsigned int, unsigned int, DWORD dwProcessId, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task`

## callers

- `0x18001e4b0`
- `0x1800206d0`

## callees

- `0x180001008`
- `0x18000115c`
- `0x180009770`
- `0x1800109f8`
- `0x180012880`
- `0x180013304`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180010b17`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180010b17`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180010adc`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x180010adc`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180010afd`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180010b6c`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180010bc9`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180010bf0`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180010afd`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180010b6c`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180010bc9`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180010bf0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010bf9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010bf9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180010a3f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180010a3f`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180010a8f`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180010a8f`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180010b4c`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180010b92`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180010b4c`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x180010b92`

## pseudocode

```c
void __fastcall DigestTelemetry::RecordDirectDigestCall(
        DigestTelemetry *this,
        char a2,
        int a3,
        int a4,
        DWORD a5,
        DWORD dwProcessId)
{
  int v8; // r12d
  HANDLE v10; // rdi
  HLOCAL v11; // rcx
  HLOCAL v12; // rbx
  __int64 v13; // rax
  __int64 v14; // r8
  int v15; // ecx
  int v16; // r8d
  bool v17; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v18[3]; // [rsp+71h] [rbp-8Fh] BYREF
  DWORD dwSize; // [rsp+74h] [rbp-8Ch] BYREF
  int v20; // [rsp+78h] [rbp-88h] BYREF
  int v21; // [rsp+7Ch] [rbp-84h] BYREF
  int v22; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v23[2]; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v24[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v25; // [rsp+A0h] [rbp-60h]
  HLOCAL hMem; // [rsp+A8h] [rbp-58h]
  __int64 v27; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE *v28; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t *v29; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v30[512]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t Filename[256]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR ExeName[264]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v8 = (int)this;
  v10 = OpenProcess(0x1000u, 0, dwProcessId);
  memset_0(Filename, 0, sizeof(Filename));
  memset_0(v30, 0, sizeof(v30));
  if ( v10 )
  {
    dwSize = 260;
    if ( QueryFullProcessImageNameW(v10, 0, ExeName, &dwSize) )
    {
      if ( _wsplitpath_s(ExeName, 0, 0, 0, 0, Filename, 0x100u, 0, 0) )
        _o_wcsncpy_s(Filename, 256, L"Unknown", -1);
      if ( !(unsigned int)_o__wcsnicmp(Filename, L"svchost", 7) )
      {
        hMem = 0;
        v25 = 0;
        v24[0] = dwProcessId;
        v24[1] = NtCurrentTeb()->SubProcessTag;
        if ( (unsigned int)I_QueryTagInformation(0, 1, v24) )
        {
          *(_OWORD *)v23 = 0;
          LODWORD(v23[0]) = dwProcessId;
          if ( !(unsigned int)I_QueryTagInformation(0, 3, v23) )
          {
            v12 = v23[1];
            if ( v23[1] )
            {
              if ( *(_DWORD *)v23[1] == 1 )
              {
                v13 = *((_QWORD *)v23[1] + 1);
                if ( *(_DWORD *)v13 == 1 )
                {
                  v14 = *(_QWORD *)(v13 + 8);
                  if ( v14 )
                  {
                    _o_wcsncpy_s(v30, 256, v14, -1);
                    v11 = v12;
                    goto LABEL_9;
                  }
                }
              }
              DigestFreeMemory(v23[1]);
            }
          }
        }
        else if ( hMem )
        {
          _o_wcsncpy_s(v30, 256, hMem, -1);
          v11 = hMem;
LABEL_9:
          DigestFreeMemory(v11);
          goto LABEL_18;
        }
        _o_wcsncpy_s(v30, 256, L"Unknown", -1);
      }
    }
  }
LABEL_18:
  CloseHandle(v10);
  if ( (unsigned int)dword_180045008 > 5 )
  {
    if ( (unsigned __int8)tlgKeywordOn(&dword_180045008, 0x400000000000LL) )
    {
      dwSize = a5;
      v28 = v30;
      v17 = g_fParameter_UseLogonCredential == 1;
      v27 = 0x1000000;
      v29 = Filename;
      v20 = a4;
      v21 = a3;
      v18[0] = a2;
      v22 = v8;
      v23[0] = (HLOCAL)1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
        v15,
        (unsigned int)byte_18003E149,
        v16,
        (unsigned int)v23,
        (__int64)&v22,
        (__int64)v18,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&dwSize,
        (__int64)&v17,
        (__int64)&v27);
    }
  }
}

```

## disassembly

```asm
0x1800109f8  push    rbp
0x1800109fa  push    rbx
0x1800109fb  push    rsi
0x1800109fc  push    rdi
0x1800109fd  push    r12
0x1800109ff  push    r14
0x180010a01  push    r15
0x180010a03  lea     rbp, [rsp-5F0h]
0x180010a0b  sub     rsp, 6F0h
0x180010a12  mov     rax, cs:__security_cookie
0x180010a19  xor     rax, rsp
0x180010a1c  mov     [rbp+620h+var_40], rax
0x180010a23  mov     ebx, [rbp+620h+dwProcessId]
0x180010a29  mov     r14d, r8d
0x180010a2c  mov     r15b, dl
0x180010a2f  mov     r12d, ecx
0x180010a32  mov     r8d, ebx; dwProcessId
0x180010a35  xor     edx, edx; bInheritHandle
0x180010a37  mov     ecx, 1000h; dwDesiredAccess
0x180010a3c  mov     esi, r9d
0x180010a3f  call    cs:__imp_OpenProcess
0x180010a45  xor     edx, edx; Val
0x180010a47  lea     rcx, [rbp+620h+var_450]; void *
0x180010a4e  mov     r8d, 200h; Size
0x180010a54  mov     rdi, rax
0x180010a57  call    memset_0
0x180010a5c  xor     edx, edx; Val
0x180010a5e  lea     rcx, [rbp+620h+var_650]; void *
0x180010a62  mov     r8d, 200h; Size
0x180010a68  call    memset_0
0x180010a6d  test    rdi, rdi
0x180010a70  jz      loc_180010BF6
0x180010a76  lea     r9, [rsp+720h+dwSize]; lpdwSize
0x180010a7b  mov     [rsp+720h+dwSize], 104h
0x180010a83  lea     r8, [rbp+620h+ExeName]; lpExeName
0x180010a8a  xor     edx, edx; dwFlags
0x180010a8c  mov     rcx, rdi; hProcess
0x180010a8f  call    cs:__imp_QueryFullProcessImageNameW
0x180010a95  test    eax, eax
0x180010a97  jz      loc_180010BF6
0x180010a9d  mov     [rsp+720h+ExtCount], 0; ExtCount
0x180010aa6  lea     rax, [rbp+620h+var_450]
0x180010aad  mov     [rsp+720h+Ext], 0; Ext
0x180010ab6  lea     rcx, [rbp+620h+ExeName]; FullPath
0x180010abd  mov     [rsp+720h+FilenameCount], 100h; FilenameCount
0x180010ac6  xor     r9d, r9d; Dir
0x180010ac9  mov     [rsp+720h+Filename], rax; Filename
0x180010ace  xor     r8d, r8d; DriveCount
0x180010ad1  xor     edx, edx; Drive
0x180010ad3  mov     [rsp+720h+DirCount], 0; DirCount
0x180010adc  call    cs:__imp__wsplitpath_s
0x180010ae2  test    eax, eax
0x180010ae4  jz      short loc_180010B03
0x180010ae6  or      r9, 0FFFFFFFFFFFFFFFFh
0x180010aea  lea     r8, aUnknown; "Unknown"
0x180010af1  mov     edx, 100h
0x180010af6  lea     rcx, [rbp+620h+var_450]
0x180010afd  call    cs:__imp__o_wcsncpy_s
0x180010b03  mov     r8d, 7
0x180010b09  lea     rdx, aSvchost; "svchost"
0x180010b10  lea     rcx, [rbp+620h+var_450]
0x180010b17  call    cs:__imp__o__wcsnicmp
0x180010b1d  test    eax, eax
0x180010b1f  jnz     loc_180010BF6
0x180010b25  xor     eax, eax
0x180010b27  lea     r8, [rbp+620h+var_688]
0x180010b2b  xorps   xmm0, xmm0
0x180010b2e  mov     [rbp+620h+hMem], rax
0x180010b32  movups  [rbp+620h+var_688], xmm0
0x180010b36  mov     dword ptr [rbp+620h+var_688], ebx
0x180010b39  mov     edx, 1
0x180010b3e  mov     rax, gs:1720h
0x180010b47  xor     ecx, ecx
0x180010b49  mov     dword ptr [rbp+620h+var_688+4], eax
0x180010b4c  call    cs:__imp_I_QueryTagInformation
0x180010b52  test    eax, eax
0x180010b54  jnz     short loc_180010B7D
0x180010b56  mov     r8, [rbp+620h+hMem]
0x180010b5a  test    r8, r8
0x180010b5d  jz      short loc_180010BDC
0x180010b5f  or      r9, 0FFFFFFFFFFFFFFFFh
0x180010b63  lea     rcx, [rbp+620h+var_650]
0x180010b67  mov     edx, 100h
0x180010b6c  call    cs:__imp__o_wcsncpy_s
0x180010b72  mov     rcx, [rbp+620h+hMem]; hMem
0x180010b76  call    DigestFreeMemory
0x180010b7b  jmp     short loc_180010BF6
0x180010b7d  xorps   xmm0, xmm0
0x180010b80  lea     r8, [rbp+620h+var_698]
0x180010b84  movups  xmmword ptr [rbp+620h+var_698], xmm0
0x180010b88  mov     edx, 3
0x180010b8d  mov     dword ptr [rbp+620h+var_698], ebx
0x180010b90  xor     ecx, ecx
0x180010b92  call    cs:__imp_I_QueryTagInformation
0x180010b98  test    eax, eax
0x180010b9a  jnz     short loc_180010BDC
0x180010b9c  mov     rbx, [rbp+620h+var_698+8]
0x180010ba0  test    rbx, rbx
0x180010ba3  jz      short loc_180010BDC
0x180010ba5  cmp     dword ptr [rbx], 1
0x180010ba8  jnz     short loc_180010BD4
0x180010baa  mov     rax, [rbx+8]
0x180010bae  cmp     dword ptr [rax], 1
0x180010bb1  jnz     short loc_180010BD4
0x180010bb3  mov     r8, [rax+8]
0x180010bb7  test    r8, r8
0x180010bba  jz      short loc_180010BD4
0x180010bbc  or      r9, 0FFFFFFFFFFFFFFFFh
0x180010bc0  lea     rcx, [rbp+620h+var_650]
0x180010bc4  mov     edx, 100h
0x180010bc9  call    cs:__imp__o_wcsncpy_s
0x180010bcf  mov     rcx, rbx
0x180010bd2  jmp     short loc_180010B76
0x180010bd4  mov     rcx, rbx; hMem
0x180010bd7  call    DigestFreeMemory
0x180010bdc  or      r9, 0FFFFFFFFFFFFFFFFh
0x180010be0  lea     r8, aUnknown; "Unknown"
0x180010be7  mov     edx, 100h
0x180010bec  lea     rcx, [rbp+620h+var_650]
0x180010bf0  call    cs:__imp__o_wcsncpy_s
0x180010bf6  mov     rcx, rdi; hObject
0x180010bf9  call    cs:__imp_CloseHandle
0x180010bff  mov     eax, cs:dword_180045008
0x180010c05  cmp     eax, 5
0x180010c08  jbe     loc_180010CDD
0x180010c0e  mov     rdx, 400000000000h
0x180010c18  lea     rcx, dword_180045008
0x180010c1f  call    _tlgKeywordOn
0x180010c24  test    al, al
0x180010c26  jz      loc_180010CDD
0x180010c2c  mov     eax, [rbp+620h+arg_20]
0x180010c32  lea     r9, [rbp+620h+var_698]
0x180010c36  cmp     cs:g_fParameter_UseLogonCredential, 1
0x180010c3d  lea     rdx, byte_18003E149
0x180010c44  mov     [rsp+720h+dwSize], eax
0x180010c48  lea     rax, [rbp+620h+var_650]
0x180010c4c  mov     [rbp+620h+var_668], rax
0x180010c50  setz    [rsp+720h+var_6B0]
0x180010c55  lea     rax, [rbp+620h+var_450]
0x180010c5c  mov     [rbp+620h+var_670], 1000000h
0x180010c64  mov     [rbp+620h+var_660], rax
0x180010c68  lea     rax, [rbp+620h+var_670]
0x180010c6c  mov     [rsp+720h+var_6C0], rax
0x180010c71  lea     rax, [rsp+720h+var_6B0]
0x180010c76  mov     [rsp+720h+var_6C8], rax
0x180010c7b  lea     rax, [rsp+720h+dwSize]
0x180010c80  mov     [rsp+720h+var_6D0], rax
0x180010c85  lea     rax, [rsp+720h+var_6A8]
0x180010c8a  mov     [rsp+720h+var_6D8], rax
0x180010c8f  lea     rax, [rsp+720h+var_6A4]
0x180010c94  mov     [rsp+720h+ExtCount], rax
0x180010c99  lea     rax, [rbp+620h+var_668]
0x180010c9d  mov     [rsp+720h+Ext], rax
0x180010ca2  lea     rax, [rbp+620h+var_660]
0x180010ca6  mov     [rsp+720h+FilenameCount], rax
0x180010cab  lea     rax, [rsp+720h+var_6AF]
0x180010cb0  mov     [rsp+720h+Filename], rax
0x180010cb5  lea     rax, [rbp+620h+var_6A0]
0x180010cb9  mov     [rsp+720h+DirCount], rax
0x180010cbe  mov     [rsp+720h+var_6A8], esi
0x180010cc2  mov     [rsp+720h+var_6A4], r14d
0x180010cc7  mov     [rsp+720h+var_6AF], r15b
0x180010ccc  mov     [rbp+620h+var_6A0], r12d
0x180010cd0  mov     [rbp+620h+var_698], 1
0x180010cd8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U4@U2@U2@U2@U3@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@533342@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x180010cdd  mov     rcx, [rbp+620h+var_40]
0x180010ce4  xor     rcx, rsp; StackCookie
0x180010ce7  call    __security_check_cookie
0x180010cec  add     rsp, 6F0h
0x180010cf3  pop     r15
0x180010cf5  pop     r14
0x180010cf7  pop     r12
0x180010cf9  pop     rdi
0x180010cfa  pop     rsi
0x180010cfb  pop     rbx
0x180010cfc  pop     rbp
0x180010cfd  retn
```
