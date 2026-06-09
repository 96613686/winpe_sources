# SspTelemetry::ClientImageInfo::ClientImageInfo(_LSA_SECPKG_FUNCTION_TABLE *)

- ea: `0x180034654`
- end: `0x180034856`
- name: `??0ClientImageInfo@SspTelemetry@@QEAA@PEAU_LSA_SECPKG_FUNCTION_TABLE@@@Z`
- size: `514`
- prototype: `__int64 __fastcall(SspTelemetry::ClientImageInfo *__hidden this, struct _LSA_SECPKG_FUNCTION_TABLE *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180034b20`
- `0x180034cd0`

## callees

- `0x180012880`
- `0x180034654`
- `0x180038010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18003478b`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18003478b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x180034818`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncat_s` at `0x180034818`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800347a0`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800347f0`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180034802`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800347a0`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800347f0`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180034802`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800347bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800347bb`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180034717`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180034717`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180034750`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180034750`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SspTelemetry::ClientImageInfo *__fastcall SspTelemetry::ClientImageInfo::ClientImageInfo(
        SspTelemetry::ClientImageInfo *this,
        struct _LSA_SECPKG_FUNCTION_TABLE *a2)
{
  char *v3; // r15
  char *v4; // r12
  HANDLE v5; // rax
  void *v6; // r14
  DWORD dwSize[4]; // [rsp+50h] [rbp-268h] BYREF
  SspTelemetry::ClientImageInfo *v9; // [rsp+60h] [rbp-258h]
  WCHAR ExeName[264]; // [rsp+70h] [rbp-248h] BYREF

  v9 = this;
  *(_OWORD *)((char *)this + 1576) = 0;
  *(_OWORD *)((char *)this + 1592) = 0;
  *((_QWORD *)this + 201) = 0;
  v3 = (char *)this + 32;
  *((_WORD *)this + 16) = 0;
  v4 = (char *)this + 544;
  *((_WORD *)this + 272) = 0;
  *((_DWORD *)this + 392) = 0;
  if ( ((int (*)(void))a2->GetClientInfo)() >= 0 )
  {
    if ( *((_DWORD *)this + 2) == dword_1800461D0 )
    {
      _o_wcsncpy_s(v3, 256, &Filename, -1);
LABEL_12:
      _o_wcsncpy_s(v4, 256, &Filename, -1);
      _o_wcsncat_s(v4, 256, &Ext, -1);
      *((_DWORD *)this + 392) = *((_DWORD *)this + 2);
      return this;
    }
    if ( _InterlockedCompareExchange16(&word_180045FC0, 1, 0) != 1 )
    {
      Filename = 0;
      Ext = 0;
      v5 = OpenProcess(0x1000u, 0, *((_DWORD *)this + 2));
      v6 = v5;
      if ( v5 )
      {
        dwSize[0] = 260;
        if ( QueryFullProcessImageNameW(v5, 0, ExeName, dwSize) )
        {
          if ( _wsplitpath_s(ExeName, 0, 0, 0, 0, &Filename, 0x100u, &Ext, 0x100u) )
          {
            Filename = 0;
            Ext = 0;
          }
          else
          {
            _o_wcsncpy_s(v3, 256, &Filename, -1);
          }
        }
        CloseHandle(v6);
      }
      dword_1800461D0 = *((_DWORD *)this + 2);
      word_180045FC0 = 0;
      goto LABEL_12;
    }
  }
  return this;
}

```

## disassembly

```asm
0x180034654  mov     [rsp+arg_10], rbx
0x180034659  mov     [rsp+arg_18], rbp
0x18003465e  push    rsi
0x18003465f  push    rdi
0x180034660  push    r12
0x180034662  push    r14
0x180034664  push    r15
0x180034666  sub     rsp, 290h
0x18003466d  mov     rax, cs:__security_cookie
0x180034674  xor     rax, rsp
0x180034677  mov     [rsp+2B8h+var_38], rax
0x18003467f  mov     rbx, rcx
0x180034682  mov     [rsp+2B8h+var_258], rcx
0x180034687  xorps   xmm0, xmm0
0x18003468a  movups  xmmword ptr [rcx+628h], xmm0
0x180034691  xorps   xmm1, xmm1
0x180034694  movups  xmmword ptr [rcx+638h], xmm1
0x18003469b  mov     qword ptr [rcx+648h], 0
0x1800346a6  lea     r15, [rcx+20h]
0x1800346aa  xor     eax, eax
0x1800346ac  mov     [r15], ax
0x1800346b0  lea     r12, [rcx+220h]
0x1800346b7  mov     [r12], ax
0x1800346bc  mov     [rcx+620h], eax
0x1800346c2  mov     rax, [rdx+80h]
0x1800346c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800346ce  test    eax, eax
0x1800346d0  js      loc_180034827
0x1800346d6  mov     eax, cs:dword_1800461D0
0x1800346dc  cmp     [rbx+8], eax
0x1800346df  jz      loc_1800347D5
0x1800346e5  xor     eax, eax
0x1800346e7  lea     ecx, [rax+1]
0x1800346ea  lock cmpxchg cs:word_180045FC0, cx
0x1800346f3  cmp     ax, cx
0x1800346f6  jz      loc_180034827
0x1800346fc  xor     eax, eax
0x1800346fe  mov     cs:Filename, ax
0x180034705  mov     cs:Ext, ax
0x18003470c  mov     r8d, [rbx+8]; dwProcessId
0x180034710  xor     edx, edx; bInheritHandle
0x180034712  mov     ecx, 1000h; dwDesiredAccess
0x180034717  call    cs:__imp_OpenProcess
0x18003471d  mov     r14, rax
0x180034720  mov     edi, 100h
0x180034725  lea     rsi, Filename
0x18003472c  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180034730  test    rax, rax
0x180034733  jz      loc_1800347C1
0x180034739  mov     [rsp+2B8h+dwSize], 104h
0x180034741  lea     r9, [rsp+2B8h+dwSize]; lpdwSize
0x180034746  lea     r8, [rsp+2B8h+ExeName]; lpExeName
0x18003474b  xor     edx, edx; dwFlags
0x18003474d  mov     rcx, rax; hProcess
0x180034750  call    cs:__imp_QueryFullProcessImageNameW
0x180034756  test    eax, eax
0x180034758  jz      short loc_1800347B8
0x18003475a  mov     [rsp+2B8h+ExtCount], rdi; ExtCount
0x18003475f  lea     rax, Ext
0x180034766  mov     [rsp+2B8h+Ext], rax; Ext
0x18003476b  mov     [rsp+2B8h+FilenameCount], rdi; FilenameCount
0x180034770  mov     [rsp+2B8h+Filename], rsi; Filename
0x180034775  mov     [rsp+2B8h+DirCount], 0; DirCount
0x18003477e  xor     r9d, r9d; Dir
0x180034781  xor     r8d, r8d; DriveCount
0x180034784  xor     edx, edx; Drive
0x180034786  lea     rcx, [rsp+2B8h+ExeName]; FullPath
0x18003478b  call    cs:__imp__wsplitpath_s
0x180034791  test    eax, eax
0x180034793  jnz     short loc_1800347A8
0x180034795  mov     r9, rbp
0x180034798  mov     r8, rsi
0x18003479b  mov     edx, edi
0x18003479d  mov     rcx, r15
0x1800347a0  call    cs:__imp__o_wcsncpy_s
0x1800347a6  jmp     short loc_1800347B8
0x1800347a8  xor     eax, eax
0x1800347aa  mov     cs:Filename, ax
0x1800347b1  mov     cs:Ext, ax
0x1800347b8  mov     rcx, r14; hObject
0x1800347bb  call    cs:__imp_CloseHandle
0x1800347c1  mov     eax, [rbx+8]
0x1800347c4  mov     cs:dword_1800461D0, eax
0x1800347ca  xor     eax, eax
0x1800347cc  xchg    ax, cs:word_180045FC0
0x1800347d3  jmp     short loc_1800347F6
0x1800347d5  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800347d9  mov     r9, rbp
0x1800347dc  lea     rsi, Filename
0x1800347e3  mov     r8, rsi
0x1800347e6  mov     edi, 100h
0x1800347eb  mov     edx, edi
0x1800347ed  mov     rcx, r15
0x1800347f0  call    cs:__imp__o_wcsncpy_s
0x1800347f6  mov     r9, rbp
0x1800347f9  mov     r8, rsi
0x1800347fc  mov     rdx, rdi
0x1800347ff  mov     rcx, r12
0x180034802  call    cs:__imp__o_wcsncpy_s
0x180034808  mov     r9, rbp
0x18003480b  lea     r8, Ext
0x180034812  mov     rdx, rdi
0x180034815  mov     rcx, r12
0x180034818  call    cs:__imp__o_wcsncat_s
0x18003481e  mov     ecx, [rbx+8]
0x180034821  mov     [rbx+620h], ecx
0x180034827  mov     rax, rbx
0x18003482a  mov     rcx, [rsp+2B8h+var_38]
0x180034832  xor     rcx, rsp; StackCookie
0x180034835  call    __security_check_cookie
0x18003483a  lea     r11, [rsp+2B8h+var_28]
0x180034842  mov     rbx, [r11+40h]
0x180034846  mov     rbp, [r11+48h]
0x18003484a  mov     rsp, r11
0x18003484d  pop     r15
0x18003484f  pop     r14
0x180034851  pop     r12
0x180034853  pop     rdi
0x180034854  pop     rsi
0x180034855  retn
```
