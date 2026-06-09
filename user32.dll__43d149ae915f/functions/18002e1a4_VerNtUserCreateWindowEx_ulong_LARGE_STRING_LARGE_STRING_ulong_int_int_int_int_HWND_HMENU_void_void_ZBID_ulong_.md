# VerNtUserCreateWindowEx(ulong,_LARGE_STRING *,_LARGE_STRING *,ulong,int,int,int,int,HWND__ *,HMENU__ *,void *,void *,ZBID,ulong,ulong)

- ea: `0x18002e1a4`
- end: `0x18002e542`
- name: `?VerNtUserCreateWindowEx@@YAPEAUHWND__@@KPEAU_LARGE_STRING@@0KHHHHPEAU1@PEAUHMENU__@@PEAX3W4ZBID@@KK@Z`
- size: `926`
- prototype: `HWND __high(unsigned int, struct _LARGE_STRING *, struct _LARGE_STRING *, unsigned int, int, int, int, int, HWND, HMENU, void *, void *, enum ZBID, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18002b854`
- `0x18002ddb0`

## callees

- `0x18002d800`
- `0x18002e1a4`
- `0x18002ec10`
- `0x18002eea4`
- `0x18002f9a8`
- `0x180096e00`

## import_xrefs

- `win32u!NtUserCreateWindowEx` at `0x18002e3d5`
- `win32u!NtUserCreateWindowEx` at `0x18002e3d5`
- `ntdll!RtlSetLastWin32Error` at `0x18002e474`
- `ntdll!RtlSetLastWin32Error` at `0x18002e474`
- `ntdll!RtlQueryInformationActiveActivationContext` at `0x18002e2d1`
- `ntdll!RtlQueryInformationActiveActivationContext` at `0x18002e2d1`
- `ntdll!RtlReleaseActivationContext` at `0x18002e402`
- `ntdll!RtlReleaseActivationContext` at `0x18002e48e`
- `ntdll!RtlReleaseActivationContext` at `0x18002e402`
- `ntdll!RtlReleaseActivationContext` at `0x18002e48e`
- `ntdll!RtlFreeHeap` at `0x18002e537`
- `ntdll!RtlFreeHeap` at `0x18002e537`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002e4fd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002e4fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e4a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e446`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e4a9`

## pseudocode

```c
__int64 __fastcall VerNtUserCreateWindowEx(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        int a13,
        int a14,
        int a15)
{
  unsigned __int16 *v16; // r12
  int v17; // edx
  struct _ACTIVATION_CONTEXT *v18; // rdi
  bool v19; // zf
  __int64 v20; // rcx
  const unsigned __int16 *v21; // rcx
  PVOID *v22; // rax
  PVOID *v23; // rsi
  __int64 v24; // rax
  int v25; // r15d
  int v26; // r13d
  __int64 Window; // rax
  __int64 v28; // r14
  CHAR *v30; // rcx
  unsigned __int16 *v31; // rcx
  int v32; // eax
  ULONG LastErrorValue; // ebx
  __int64 v34; // [rsp+98h] [rbp-78h]
  int v37; // [rsp+C0h] [rbp-50h]
  unsigned __int16 *v38; // [rsp+C8h] [rbp-48h] BYREF
  HANDLE handle; // [rsp+D0h] [rbp-40h] BYREF
  HMODULE hLibModule; // [rsp+D8h] [rbp-38h] BYREF
  PVOID v41[4]; // [rsp+E0h] [rbp-30h] BYREF
  __int128 pvBuffer; // [rsp+100h] [rbp-10h] BYREF
  __int64 v43; // [rsp+110h] [rbp+0h]
  __int64 v44; // [rsp+118h] [rbp+8h]
  __int64 v45; // [rsp+120h] [rbp+10h]
  __int64 v46; // [rsp+128h] [rbp+18h]
  __int64 v47; // [rsp+130h] [rbp+20h]
  unsigned __int16 v48[256]; // [rsp+140h] [rbp+30h] BYREF

  v16 = 0;
  v17 = a15;
  v18 = 0;
  v46 = a9;
  v45 = a10;
  v44 = a11;
  v43 = a12;
  v19 = (*(_BYTE *)gpsi & 4) == 0;
  v47 = a3;
  memset(v41, 0, sizeof(v41));
  v38 = 0;
  hLibModule = 0;
  handle = 0;
  LODWORD(v41[3]) = 0;
  if ( (gdwRegisteredClasses & 0x80u) == 0 && !v19 )
  {
    if ( !(unsigned int)RegisterIMEClass() )
      return 0;
    v17 = a15;
  }
  v20 = 0;
  v34 = 0;
  v37 = v17 & 0x40000000;
  if ( (v17 & 0x40000000) != 0 )
  {
    pvBuffer = 0;
    RtlQueryInformationActiveActivationContext(1u, &pvBuffer, 0x10u, 0);
    if ( (BYTE8(pvBuffer) & 1) != 0 )
      RtlReleaseActivationContext((HANDLE)pvBuffer);
    else
      v34 = pvBuffer;
    if ( (a2 & 0xFFFFFFFFFFFF0000uLL) != 0 )
      v21 = *(const unsigned __int16 **)(a2 + 8);
    else
      v21 = (const unsigned __int16 *)a2;
    v22 = (PVOID *)ClassNameToVersion(v21, v48, 0x200u, &v38, (struct _ACTIVATION_CONTEXT **)&handle, 0);
    v23 = v22;
    if ( v22 )
    {
      if ( ((unsigned __int64)v22 & 0xFFFFFFFFFFFF0000uLL) != 0 )
      {
        v41[1] = v22;
        HIDWORD(v41[0]) &= ~0x80000000;
        v24 = -1;
        do
          ++v24;
        while ( *((_WORD *)v23 + v24) );
        v23 = v41;
        LODWORD(v41[0]) = 2 * v24;
        HIDWORD(v41[0]) = (2 * v24 + 2) & 0x7FFFFFFF;
      }
      v16 = v38;
      v18 = (struct _ACTIVATION_CONTEXT *)handle;
      v20 = v34;
      v17 = a15;
      goto LABEL_15;
    }
    return 0;
  }
  v23 = (PVOID *)a2;
LABEL_15:
  v25 = 0;
  v26 = 0;
  do
  {
    while ( 1 )
    {
      Window = NtUserCreateWindowEx(a1, a2, v23, v47, a4, a5, a6, a7, a8, v46, v45, v44, v43, a13, v17, a14, v20);
      v28 = Window;
      if ( v26 || gdwRegisteredClasses == gdwRegisteredClassesMask )
      {
        if ( Window )
          goto LABEL_19;
        break;
      }
      if ( Window )
        goto LABEL_19;
      if ( GetLastError() != 1407 )
        break;
      v30 = (a2 & 0xFFFFFFFFFFFF0000uLL) != 0 ? *(CHAR **)(a2 + 8) : (CHAR *)a2;
      if ( !(unsigned int)RegisterDefaultClass(v30, 0) )
        break;
      v26 = 1;
      RtlSetLastWin32Error(0);
      v20 = v34;
      v17 = a15;
    }
    if ( !v37 || !v16 || v25 || GetLastError() != 1407 )
      break;
    v31 = (a2 & 0xFFFFFFFFFFFF0000uLL) != 0 ? *(unsigned __int16 **)(a2 + 8) : (unsigned __int16 *)a2;
    v32 = VersionRegisterClass(v31, v16, v18, &hLibModule);
    v20 = v34;
    v25 = v32;
    v17 = a15;
  }
  while ( v32 );
  if ( hLibModule )
  {
    LastErrorValue = NtCurrentTeb()->LastErrorValue;
    FreeLibrary(hLibModule);
    NtCurrentTeb()->LastErrorValue = LastErrorValue;
  }
LABEL_19:
  if ( v18 )
    RtlReleaseActivationContext(v18);
  if ( LODWORD(v41[3]) )
    RtlFreeHeap(pUserHeap, 0, v41[1]);
  return v28;
}

```

## disassembly

```asm
0x18002e1a4  push    rbp
0x18002e1a6  push    rbx
0x18002e1a7  push    rsi
0x18002e1a8  push    rdi
0x18002e1a9  push    r12
0x18002e1ab  push    r13
0x18002e1ad  push    r14
0x18002e1af  push    r15
0x18002e1b1  lea     rbp, [rsp-248h]
0x18002e1b9  sub     rsp, 358h
0x18002e1c0  mov     rax, cs:__security_cookie
0x18002e1c7  xor     rax, rsp
0x18002e1ca  mov     [rbp+280h+var_50], rax
0x18002e1d1  mov     eax, [rbp+280h+arg_20]
0x18002e1d7  xor     r14d, r14d
0x18002e1da  test    byte ptr cs:?gdwRegisteredClasses@@3KA, 80h; ulong gdwRegisteredClasses
0x18002e1e1  xorps   xmm0, xmm0
0x18002e1e4  mov     [rbp+280h+var_2DC], eax
0x18002e1e7  mov     rbx, rdx
0x18002e1ea  mov     eax, [rbp+280h+arg_28]
0x18002e1f0  mov     r12d, r14d
0x18002e1f3  mov     edx, [rbp+280h+arg_70]
0x18002e1f9  mov     edi, r14d
0x18002e1fc  mov     [rbp+280h+var_2E0], eax
0x18002e1ff  mov     eax, [rbp+280h+arg_30]
0x18002e205  mov     [rbp+280h+var_2E4], eax
0x18002e208  mov     eax, [rbp+280h+arg_38]
0x18002e20e  mov     [rbp+280h+var_2E8], eax
0x18002e211  mov     rax, [rbp+280h+arg_40]
0x18002e218  mov     [rbp+280h+var_268], rax
0x18002e21c  mov     rax, [rbp+280h+arg_48]
0x18002e223  mov     [rbp+280h+var_270], rax
0x18002e227  mov     rax, [rbp+280h+arg_50]
0x18002e22e  mov     [rbp+280h+var_278], rax
0x18002e232  mov     rax, [rbp+280h+arg_58]
0x18002e239  mov     [rbp+280h+var_280], rax
0x18002e23d  mov     eax, [rbp+280h+arg_60]
0x18002e243  mov     [rbp+280h+var_2EC], eax
0x18002e246  mov     eax, [rbp+280h+arg_68]
0x18002e24c  mov     [rbp+280h+var_2F0], eax
0x18002e24f  mov     rax, cs:gpsi
0x18002e256  mov     [rbp+280h+var_2D4], ecx
0x18002e259  setz    cl
0x18002e25c  movups  xmmword ptr [rbp+280h+P], xmm0
0x18002e260  mov     [rbp+280h+var_2D8], r9d
0x18002e264  test    byte ptr [rax], 4
0x18002e267  movups  xmmword ptr [rbp+280h+P+0Ch], xmm0
0x18002e26b  setnz   al
0x18002e26e  mov     [rbp+280h+var_260], r8
0x18002e272  mov     [rbp+280h+var_300], edx
0x18002e275  mov     [rbp+280h+var_2B0], r14d
0x18002e279  mov     [rbp+280h+var_2C8], r14
0x18002e27d  mov     [rbp+280h+hLibModule], r14
0x18002e281  mov     [rbp+280h+handle], r14
0x18002e285  mov     [rbp+280h+var_298], r14d
0x18002e289  test    al, cl
0x18002e28b  jz      short loc_18002E29D
0x18002e28d  call    ?RegisterIMEClass@@YAHXZ; RegisterIMEClass(void)
0x18002e292  test    eax, eax
0x18002e294  jz      loc_18002E486
0x18002e29a  mov     edx, [rbp+280h+var_300]
0x18002e29d  mov     eax, edx
0x18002e29f  mov     rcx, r14
0x18002e2a2  and     eax, 40000000h
0x18002e2a7  mov     [rbp+280h+var_2F8], rcx
0x18002e2ab  mov     [rbp+280h+var_2D0], eax
0x18002e2ae  mov     r15, 0FFFFFFFFFFFF0000h
0x18002e2b5  jz      loc_18002E522
0x18002e2bb  xor     r9d, r9d; pcbWrittenOrRequired
0x18002e2be  lea     rdx, [rbp+280h+pvBuffer]; pvBuffer
0x18002e2c2  xorps   xmm0, xmm0
0x18002e2c5  movups  [rbp+280h+pvBuffer], xmm0
0x18002e2c9  lea     r8d, [r9+10h]; cbBuffer
0x18002e2cd  lea     ecx, [r9+1]; ulInfoClass
0x18002e2d1  call    cs:__imp_RtlQueryInformationActiveActivationContext
0x18002e2d7  test    byte ptr [rbp+280h+pvBuffer+8], 1
0x18002e2db  jnz     loc_18002E48A
0x18002e2e1  mov     rax, qword ptr [rbp+280h+pvBuffer]
0x18002e2e5  mov     [rbp+280h+var_2F8], rax
0x18002e2e9  test    r15, rbx
0x18002e2ec  jnz     loc_18002E438
0x18002e2f2  mov     rcx, rbx; Src
0x18002e2f5  lea     rax, [rbp+280h+handle]
0x18002e2f9  mov     [rsp+390h+var_368], r14d; int
0x18002e2fe  lea     r9, [rbp+280h+var_2C8]; unsigned __int16 **
0x18002e302  mov     [rsp+390h+var_370], rax; struct _ACTIVATION_CONTEXT **
0x18002e307  mov     r8d, 200h; MbSize
0x18002e30d  lea     rdx, [rbp+280h+var_250]; unsigned __int16 *
0x18002e311  call    ?ClassNameToVersion@@YAPEAGPEBGPEAGIPEAPEAGPEAPEAU_ACTIVATION_CONTEXT@@H@Z; ClassNameToVersion(ushort const *,ushort *,uint,ushort * *,_ACTIVATION_CONTEXT * *,int)
0x18002e316  mov     rsi, rax
0x18002e319  test    rax, rax
0x18002e31c  jz      loc_18002E486
0x18002e322  test    r15, rax
0x18002e325  jz      short loc_18002E352
0x18002e327  mov     ecx, 7FFFFFFFh
0x18002e32c  mov     [rbp+280h+P+4], rax
0x18002e330  and     dword ptr [rbp+280h+P], ecx
0x18002e333  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e337  inc     rax
0x18002e33a  cmp     [rsi+rax*2], r14w
0x18002e33f  jnz     short loc_18002E337
0x18002e341  add     eax, eax
0x18002e343  lea     rsi, [rbp+280h+var_2B0]
0x18002e347  mov     [rbp+280h+var_2B0], eax
0x18002e34a  add     eax, 2
0x18002e34d  and     eax, ecx
0x18002e34f  mov     dword ptr [rbp+280h+P], eax
0x18002e352  mov     r12, [rbp+280h+var_2C8]
0x18002e356  mov     rdi, [rbp+280h+handle]
0x18002e35a  mov     rcx, [rbp+280h+var_2F8]
0x18002e35e  mov     edx, [rbp+280h+var_300]
0x18002e361  mov     r15d, r14d
0x18002e364  mov     r13d, r14d
0x18002e367  mov     eax, [rbp+280h+var_2F0]
0x18002e36a  mov     r8, rsi
0x18002e36d  mov     r9, [rbp+280h+var_260]
0x18002e371  mov     [rsp+390h+var_310], rcx
0x18002e379  mov     ecx, [rbp+280h+var_2D4]
0x18002e37c  mov     [rsp+390h+var_318], eax
0x18002e380  mov     eax, [rbp+280h+var_2EC]
0x18002e383  mov     [rsp+390h+var_320], edx
0x18002e387  mov     rdx, rbx
0x18002e38a  mov     [rsp+390h+var_328], eax
0x18002e38e  mov     rax, [rbp+280h+var_280]
0x18002e392  mov     [rsp+390h+var_330], rax
0x18002e397  mov     rax, [rbp+280h+var_278]
0x18002e39b  mov     [rsp+390h+var_338], rax
0x18002e3a0  mov     rax, [rbp+280h+var_270]
0x18002e3a4  mov     [rsp+390h+var_340], rax
0x18002e3a9  mov     rax, [rbp+280h+var_268]
0x18002e3ad  mov     [rsp+390h+var_348], rax
0x18002e3b2  mov     eax, [rbp+280h+var_2E8]
0x18002e3b5  mov     [rsp+390h+var_350], eax
0x18002e3b9  mov     eax, [rbp+280h+var_2E4]
0x18002e3bc  mov     [rsp+390h+var_358], eax
0x18002e3c0  mov     eax, [rbp+280h+var_2E0]
0x18002e3c3  mov     [rsp+390h+var_360], eax
0x18002e3c7  mov     eax, [rbp+280h+var_2DC]
0x18002e3ca  mov     [rsp+390h+var_368], eax
0x18002e3ce  mov     eax, [rbp+280h+var_2D8]
0x18002e3d1  mov     dword ptr [rsp+390h+var_370], eax
0x18002e3d5  call    cs:__imp_NtUserCreateWindowEx
0x18002e3db  mov     r14, rax
0x18002e3de  test    r13d, r13d
0x18002e3e1  jnz     short loc_18002E3F1
0x18002e3e3  mov     ecx, cs:?gdwRegisteredClassesMask@@3KA; ulong gdwRegisteredClassesMask
0x18002e3e9  cmp     cs:?gdwRegisteredClasses@@3KA, ecx; ulong gdwRegisteredClasses
0x18002e3ef  jnz     short loc_18002E441
0x18002e3f1  test    r14, r14
0x18002e3f4  jz      loc_18002E499
0x18002e3fa  test    rdi, rdi
0x18002e3fd  jz      short loc_18002E408
0x18002e3ff  mov     rcx, rdi; handle
0x18002e402  call    cs:__imp_RtlReleaseActivationContext
0x18002e408  cmp     [rbp+280h+var_298], 0
0x18002e40c  jnz     loc_18002E52A
0x18002e412  mov     rax, r14
0x18002e415  mov     rcx, [rbp+280h+var_50]
0x18002e41c  xor     rcx, rsp; StackCookie
0x18002e41f  call    __security_check_cookie
0x18002e424  add     rsp, 358h
0x18002e42b  pop     r15
0x18002e42d  pop     r14
0x18002e42f  pop     r13
0x18002e431  pop     r12
0x18002e433  pop     rdi
0x18002e434  pop     rsi
0x18002e435  pop     rbx
0x18002e436  pop     rbp
0x18002e437  retn
0x18002e438  mov     rcx, [rbx+8]
0x18002e43c  jmp     loc_18002E2F5
0x18002e441  test    r14, r14
0x18002e444  jnz     short loc_18002E3FA
0x18002e446  call    cs:__imp_GetLastError
0x18002e44c  cmp     eax, 57Fh
0x18002e451  jnz     short loc_18002E499
0x18002e453  test    rbx, 0FFFFFFFFFFFF0000h
0x18002e45a  jnz     loc_18002E514
0x18002e460  mov     rcx, rbx; MultiByteString
0x18002e463  xor     edx, edx; int
0x18002e465  call    ?RegisterDefaultClass@@YAHPEBGH@Z; RegisterDefaultClass(ushort const *,int)
0x18002e46a  test    eax, eax
0x18002e46c  jz      short loc_18002E499
0x18002e46e  xor     ecx, ecx; LastError
0x18002e470  lea     r13d, [rcx+1]
0x18002e474  call    cs:__imp_RtlSetLastWin32Error
0x18002e47a  mov     rcx, [rbp+280h+var_2F8]
0x18002e47e  mov     edx, [rbp+280h+var_300]
0x18002e481  jmp     loc_18002E367
0x18002e486  xor     eax, eax
0x18002e488  jmp     short loc_18002E415
0x18002e48a  mov     rcx, qword ptr [rbp+280h+pvBuffer]; handle
0x18002e48e  call    cs:__imp_RtlReleaseActivationContext
0x18002e494  jmp     loc_18002E2E9
0x18002e499  cmp     [rbp+280h+var_2D0], 0
0x18002e49d  jz      short loc_18002E4E4
0x18002e49f  test    r12, r12
0x18002e4a2  jz      short loc_18002E4E4
0x18002e4a4  test    r15d, r15d
0x18002e4a7  jnz     short loc_18002E4E4
0x18002e4a9  call    cs:__imp_GetLastError
0x18002e4af  cmp     eax, 57Fh
0x18002e4b4  jnz     short loc_18002E4E4
0x18002e4b6  test    rbx, 0FFFFFFFFFFFF0000h
0x18002e4bd  jz      short loc_18002E51D
0x18002e4bf  mov     rcx, [rbx+8]; unsigned __int16 *
0x18002e4c3  lea     r9, [rbp+280h+hLibModule]; HINSTANCE *
0x18002e4c7  mov     r8, rdi; struct _ACTIVATION_CONTEXT *
0x18002e4ca  mov     rdx, r12; unsigned __int16 *
0x18002e4cd  call    ?VersionRegisterClass@@YAHPEAG0PEAU_ACTIVATION_CONTEXT@@PEAPEAUHINSTANCE__@@@Z; VersionRegisterClass(ushort *,ushort *,_ACTIVATION_CONTEXT *,HINSTANCE__ * *)
0x18002e4d2  mov     rcx, [rbp+280h+var_2F8]
0x18002e4d6  mov     r15d, eax
0x18002e4d9  mov     edx, [rbp+280h+var_300]
0x18002e4dc  test    eax, eax
0x18002e4de  jnz     loc_18002E367
0x18002e4e4  mov     rcx, [rbp+280h+hLibModule]; hLibModule
0x18002e4e8  test    rcx, rcx
0x18002e4eb  jz      loc_18002E3FA
0x18002e4f1  mov     rax, gs:30h
0x18002e4fa  mov     ebx, [rax+68h]
0x18002e4fd  call    cs:__imp_FreeLibrary
0x18002e503  mov     rax, gs:30h
0x18002e50c  mov     [rax+68h], ebx
0x18002e50f  jmp     loc_18002E3FA
0x18002e514  mov     rcx, [rbx+8]
0x18002e518  jmp     loc_18002E463
0x18002e51d  mov     rcx, rbx
0x18002e520  jmp     short loc_18002E4C3
0x18002e522  mov     rsi, rbx
0x18002e525  jmp     loc_18002E361
0x18002e52a  mov     r8, [rbp+280h+P+4]; P
0x18002e52e  xor     edx, edx; Flags
0x18002e530  mov     rcx, cs:pUserHeap; HeapHandle
0x18002e537  call    cs:__imp_RtlFreeHeap
0x18002e53d  jmp     loc_18002E412
```
