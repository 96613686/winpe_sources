# CCopyError::Report(void *,ushort const *,ushort const *,ulong)

- ea: `0x180006e18`
- end: `0x180006fff`
- name: `?Report@CCopyError@@QEAAJPEAXPEBG1K@Z`
- size: `487`
- prototype: `__int64 __fastcall(CCopyError *__hidden this, void *, const unsigned __int16 *, const unsigned __int16 *, DWORD dwMessageId)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180008d00`
- `0x18000ab88`
- `0x18000bd3c`

## callees

- `0x1800040b0`
- `0x180004110`
- `0x1800055d8`
- `0x1800065d8`
- `0x180006e18`
- `0x18000e640`
- `0x18001aca8`
- `0x18001b3b4`
- `0x18001b6a4`
- `0x18001bd94`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006f50`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006f50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006f9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006f9d`

## string_xrefs

- `0x180006e8e`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
__int64 __fastcall CCopyError::Report(
        CCopyError *this,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        DWORD dwMessageId)
{
  char v5; // di
  int v6; // r15d
  int v7; // r14d
  int v8; // ebx
  int v9; // eax
  int v10; // ecx
  const wchar_t *v11; // rax
  const wchar_t *v12; // rcx
  int lpBuffer; // [rsp+20h] [rbp-71h]
  WCHAR Buffer[4]; // [rsp+40h] [rbp-51h] BYREF
  __int64 v16[3]; // [rsp+48h] [rbp-49h] BYREF
  int v17; // [rsp+60h] [rbp-31h] BYREF
  __int64 v18; // [rsp+68h] [rbp-29h]
  __int64 v19; // [rsp+70h] [rbp-21h]
  int v20; // [rsp+78h] [rbp-19h]
  __int128 v21; // [rsp+80h] [rbp-11h]
  struct _EVENT_DATA_DESCRIPTOR v22; // [rsp+90h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]

  v5 = 0;
  v6 = (int)a4;
  *(_DWORD *)Buffer = 0;
  v7 = (int)a3;
  v8 = _InterlockedIncrement((volatile signed __int32 *)this);
  if ( v8 <= 10 )
  {
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
    if ( a2 )
    {
      v9 = CThreadContext::ImpersonateUser((CThreadContext *)&v17, a2);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x57,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
          (const char *)(unsigned int)v9,
          lpBuffer);
    }
    if ( v8 >= 10 )
    {
      if ( (Microsoft_Windows_User_Profiles_GeneralEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(
          (__int64)this,
          (const EVENT_DESCRIPTOR *)EVENT_TOO_MANY_COPY_ERRORS,
          (__int64)a3,
          1u,
          &v22);
    }
    else
    {
      memset(v16, 0, sizeof(v16));
      if ( dwMessageId == 6002
        && (v22.Ptr = 0,
            Buffer[0] = 0,
            Windows::Internal::ResourceString::FindAndSize(
              &_ImageBase,
              (unsigned int)a2,
              (unsigned __int16)a3,
              (const unsigned __int16 **)&v22,
              Buffer))
        && (int)Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Initialize(
                  v16,
                  v22.Ptr,
                  Buffer[0]) >= 0 )
      {
        if ( (Microsoft_Windows_User_Profiles_GeneralEnableBits & 1) != 0 )
          McTemplateU0zzz_EventWriteTransfer(v10, (unsigned int)EVENT_COPYERROR, v7, v6, v16[0]);
      }
      else
      {
        if ( (Microsoft_Windows_User_Profiles_GeneralEnableBits & 1) != 0 )
        {
          if ( FormatMessageW(0x1100u, 0, dwMessageId, 0, Buffer, 1u, 0) )
          {
            v11 = *(const wchar_t **)Buffer;
          }
          else
          {
            v11 = 0;
            *(_QWORD *)Buffer = 0;
          }
          v12 = L"???";
          if ( v11 )
            v12 = v11;
          McTemplateU0zzz_EventWriteTransfer((_DWORD)v12, (unsigned int)EVENT_COPYERROR, v7, v6, (__int64)v12);
          v5 = 1;
        }
        if ( (v5 & 1) != 0 )
          LocalFree(*(HLOCAL *)Buffer);
      }
      Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(v16);
    }
    CThreadContext::~CThreadContext((CThreadContext *)&v17);
  }
  return 0;
}

```

## disassembly

```asm
0x180006e18  push    rbp
0x180006e1a  push    rbx
0x180006e1b  push    rsi
0x180006e1c  push    rdi
0x180006e1d  push    r13
0x180006e1f  push    r14
0x180006e21  push    r15
0x180006e23  lea     rbp, [rsp-1Fh]
0x180006e28  sub     rsp, 0B0h
0x180006e2f  mov     rax, cs:__security_cookie
0x180006e36  xor     rax, rsp
0x180006e39  mov     [rbp+4Fh+var_40], rax
0x180006e3d  mov     esi, [rbp+4Fh+dwMessageId]
0x180006e40  xor     edi, edi
0x180006e42  mov     r15, r9
0x180006e45  mov     dword ptr [rbp+4Fh+Buffer], edi
0x180006e48  mov     r14, r8
0x180006e4b  lea     r13d, [rdi+1]
0x180006e4f  mov     ebx, r13d
0x180006e52  lock xadd [rcx], ebx
0x180006e56  add     ebx, r13d
0x180006e59  cmp     ebx, 0Ah
0x180006e5c  jg      loc_180006FDE
0x180006e62  mov     [rbp+4Fh+var_80], edi
0x180006e65  xorps   xmm0, xmm0
0x180006e68  mov     [rbp+4Fh+var_78], rdi
0x180006e6c  mov     [rbp+4Fh+var_70], rdi
0x180006e70  mov     [rbp+4Fh+var_68], edi
0x180006e73  movdqu  [rbp+4Fh+var_60], xmm0
0x180006e78  test    rdx, rdx
0x180006e7b  jz      short loc_180006EA0
0x180006e7d  lea     rcx, [rbp+4Fh+var_80]; this
0x180006e81  call    ?ImpersonateUser@CThreadContext@@QEAAJPEAX@Z; CThreadContext::ImpersonateUser(void *)
0x180006e86  test    eax, eax
0x180006e88  jns     short loc_180006EA0
0x180006e8a  mov     rcx, [rbp+57h]; this
0x180006e8e  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180006e95  mov     r9d, eax; char *
0x180006e98  lea     edx, [rdi+57h]; void *
0x180006e9b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180006ea0  cmp     ebx, 0Ah
0x180006ea3  jge     loc_180006FB4
0x180006ea9  mov     [rbp+4Fh+var_98], rdi
0x180006ead  mov     [rbp+4Fh+var_90], rdi
0x180006eb1  mov     [rbp+4Fh+var_88], rdi
0x180006eb5  cmp     esi, 1772h
0x180006ebb  jnz     short loc_180006F27
0x180006ebd  xor     eax, eax
0x180006ebf  mov     qword ptr [rbp+4Fh+var_50], rdi
0x180006ec3  mov     [rbp+4Fh+Buffer], ax
0x180006ec7  lea     r9, [rbp+4Fh+var_50]; unsigned __int16 **
0x180006ecb  lea     rax, [rbp+4Fh+Buffer]
0x180006ecf  lea     rcx, __ImageBase; hModule
0x180006ed6  mov     [rsp+0E0h+lpBuffer], rax; unsigned __int16 *
0x180006edb  call    ?FindAndSize@ResourceString@Internal@Windows@@SA_NPEAUHINSTANCE__@@IGPEAPEBGPEAG@Z; Windows::Internal::ResourceString::FindAndSize(HINSTANCE__ *,uint,ushort,ushort const * *,ushort *)
0x180006ee0  test    al, al
0x180006ee2  jz      short loc_180006F27
0x180006ee4  movzx   r8d, [rbp+4Fh+Buffer]
0x180006ee9  lea     rcx, [rbp+4Fh+var_98]
0x180006eed  mov     rdx, qword ptr [rbp+4Fh+var_50]
0x180006ef1  call    ?_Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180006ef6  test    eax, eax
0x180006ef8  js      short loc_180006F27
0x180006efa  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, r13b
0x180006f01  jz      loc_180006FA9
0x180006f07  mov     rax, [rbp+4Fh+var_98]
0x180006f0b  lea     rdx, EVENT_COPYERROR
0x180006f12  mov     r9, r15
0x180006f15  mov     [rsp+0E0h+lpBuffer], rax
0x180006f1a  mov     r8, r14
0x180006f1d  call    McTemplateU0zzz_EventWriteTransfer
0x180006f22  jmp     loc_180006FA9
0x180006f27  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, r13b
0x180006f2e  jz      short loc_180006F94
0x180006f30  mov     [rsp+0E0h+Arguments], rdi; Arguments
0x180006f35  lea     rax, [rbp+4Fh+Buffer]
0x180006f39  mov     [rsp+0E0h+nSize], r13d; nSize
0x180006f3e  xor     r9d, r9d; dwLanguageId
0x180006f41  mov     r8d, esi; dwMessageId
0x180006f44  mov     [rsp+0E0h+lpBuffer], rax; lpBuffer
0x180006f49  xor     edx, edx; lpSource
0x180006f4b  mov     ecx, 1100h; dwFlags
0x180006f50  call    cs:__imp_FormatMessageW
0x180006f57  nop     dword ptr [rax+rax+00h]
0x180006f5c  test    eax, eax
0x180006f5e  jnz     short loc_180006F68
0x180006f60  xor     eax, eax
0x180006f62  mov     qword ptr [rbp+4Fh+Buffer], rax
0x180006f66  jmp     short loc_180006F6C
0x180006f68  mov     rax, qword ptr [rbp+4Fh+Buffer]
0x180006f6c  test    rax, rax
0x180006f6f  lea     rcx, asc_180020C28; "???"
0x180006f76  mov     r9, r15
0x180006f79  lea     rdx, EVENT_COPYERROR
0x180006f80  cmovnz  rcx, rax
0x180006f84  mov     r8, r14
0x180006f87  mov     [rsp+0E0h+lpBuffer], rcx
0x180006f8c  call    McTemplateU0zzz_EventWriteTransfer
0x180006f91  mov     edi, r13d
0x180006f94  test    r13b, dil
0x180006f97  jz      short loc_180006FA9
0x180006f99  mov     rcx, qword ptr [rbp+4Fh+Buffer]; hMem
0x180006f9d  call    cs:__imp_LocalFree
0x180006fa4  nop     dword ptr [rax+rax+00h]
0x180006fa9  lea     rcx, [rbp+4Fh+var_98]
0x180006fad  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180006fb2  jmp     short loc_180006FD5
0x180006fb4  test    byte ptr cs:Microsoft_Windows_User_Profiles_GeneralEnableBits, r13b
0x180006fbb  jz      short loc_180006FD5
0x180006fbd  lea     rax, [rbp+4Fh+var_50]
0x180006fc1  mov     r9d, r13d
0x180006fc4  lea     rdx, EVENT_TOO_MANY_COPY_ERRORS
0x180006fcb  mov     [rsp+0E0h+lpBuffer], rax
0x180006fd0  call    McGenEventWrite_EventWriteTransfer
0x180006fd5  lea     rcx, [rbp+4Fh+var_80]; this
0x180006fd9  call    ??1CThreadContext@@QEAA@XZ; CThreadContext::~CThreadContext(void)
0x180006fde  xor     eax, eax
0x180006fe0  mov     rcx, [rbp+4Fh+var_40]
0x180006fe4  xor     rcx, rsp; StackCookie
0x180006fe7  call    __security_check_cookie
0x180006fec  add     rsp, 0B0h
0x180006ff3  pop     r15
0x180006ff5  pop     r14
0x180006ff7  pop     r13
0x180006ff9  pop     rdi
0x180006ffa  pop     rsi
0x180006ffb  pop     rbx
0x180006ffc  pop     rbp
0x180006ffd  retn
```
