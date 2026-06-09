# CVssRegistryKey::DeleteSubkey(ushort const *,...)

- ea: `0x18003847c`
- end: `0x1800386c5`
- name: `?DeleteSubkey@CVssRegistryKey@@QEAAXPEBGZZ`
- size: `585`
- prototype: `void(HKEY *this, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002f070`

## callees

- `0x180001580`
- `0x18000212c`
- `0x180033a8c`
- `0x180033c78`
- `0x18003649c`
- `0x180037080`
- `0x18003847c`
- `0x18003a534`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180038552`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180038552`

## string_xrefs

- `0x1800384b7`: `base\stor\vss\modules\registry\registry.cxx`
- `0x1800384c3`: `CVssRegistryKey::DeleteSubkey`
- `0x1800385ab`: `Key with path %s\%s not found`
- `0x18003862f`: `SHDeleteKey(%ld[%s],%s)`

## pseudocode

```c
void CVssRegistryKey::DeleteSubkey(HKEY *this, const unsigned __int16 *a2, ...)
{
  unsigned __int64 v3; // rdx
  int v4; // ebx
  LSTATUS v5; // eax
  unsigned int v6; // ebx
  HKEY v7; // rsi
  HKEY v8; // rdi
  const unsigned __int16 *v9; // [rsp+50h] [rbp-B8h] BYREF
  const wchar_t *v10; // [rsp+58h] [rbp-B0h]
  const unsigned __int16 *v11; // [rsp+60h] [rbp-A8h]
  int v12; // [rsp+68h] [rbp-A0h]
  int v13; // [rsp+6Ch] [rbp-9Ch]
  int v14; // [rsp+70h] [rbp-98h]
  _BYTE v15[120]; // [rsp+78h] [rbp-90h] BYREF
  int v16; // [rsp+F0h] [rbp-18h]
  LPVOID v17; // [rsp+F8h] [rbp-10h] BYREF
  int v18; // [rsp+100h] [rbp-8h]
  WCHAR SubKey[264]; // [rsp+168h] [rbp+60h] BYREF
  va_list va; // [rsp+3D8h] [rbp+2D0h] BYREF

  va_start(va, a2);
  v9 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v10 = L"CVssRegistryKey::DeleteSubkey";
  v11 = L"REGREGSC";
  v12 = 173;
  v13 = 11;
  v14 = 255;
  v16 = 0x1000000;
  memset_0(v15, 0, sizeof(v15));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v17, (__int64)&v9, 0);
  v4 = StringCchVPrintfW(SubKey, v3, a2, va);
  v18 = v4;
  if ( v4 < 0 )
  {
    v9 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v10 = L"CVssRegistryKey::DeleteSubkey";
    v11 = L"REGREGSC";
    v12 = 184;
    v13 = 11;
    v14 = 255;
    v16 = 0x1000000;
    memset_0(v15, 0, sizeof(v15));
    CVssFunctionTracer::TranslateGenericError(&v17, &v9, (unsigned int)v4, L"StringCchVPrintfW()");
  }
  v5 = RegDeleteTreeW(this[1], SubKey);
  v6 = v5;
  if ( v5 == 2 )
  {
    v9 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v10 = L"CVssRegistryKey::DeleteSubkey";
    v11 = L"REGREGSC";
    v12 = 192;
    v13 = 11;
    v14 = 255;
    v16 = 0x1000000;
    memset_0(v15, 0, sizeof(v15));
    CVssFunctionTracer::Throw(&v17, &v9, 2147754760LL, L"Key with path %s\\%s not found", this[3], SubKey);
  }
  if ( v5 )
  {
    v7 = this[3];
    v8 = this[1];
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    v9 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
    v10 = L"CVssRegistryKey::DeleteSubkey";
    v11 = L"REGREGSC";
    v12 = 195;
    v13 = 11;
    v14 = 255;
    v16 = 0x1000000;
    memset_0(v15, 0, sizeof(v15));
    CVssFunctionTracer::TranslateGenericError(&v17, &v9, v6, L"SHDeleteKey(%ld[%s],%s)", v8, v7, SubKey);
  }
  CVssFunctionTracer::~CVssFunctionTracer(&v17);
}

```

## disassembly

```asm
0x18003847c  mov     rax, rsp
0x18003847f  mov     [rax+10h], rdx
0x180038483  mov     [rax+18h], r8
0x180038487  mov     [rax+20h], r9
0x18003848b  push    rbp
0x18003848c  push    rbx
0x18003848d  push    rsi
0x18003848e  push    rdi
0x18003848f  push    r12
0x180038491  push    r13
0x180038493  push    r15
0x180038495  lea     rbp, [rax-2B8h]
0x18003849c  sub     rsp, 380h
0x1800384a3  mov     rax, cs:__security_cookie
0x1800384aa  xor     rax, rsp
0x1800384ad  mov     [rbp+2B0h+var_40], rax
0x1800384b4  mov     rdi, rcx
0x1800384b7  lea     r15, aBaseStorVssMod_10; "base\\stor\\vss\\modules\\registry\\reg"...
0x1800384be  mov     [rsp+3B0h+var_368], r15
0x1800384c3  lea     r12, aCvssregistryke_4; "CVssRegistryKey::DeleteSubkey"
0x1800384ca  mov     [rsp+3B0h+var_360], r12
0x1800384cf  lea     r13, aRegregsc; "REGREGSC"
0x1800384d6  mov     qword ptr [rsp+3B0h+var_358], r13
0x1800384db  mov     [rsp+3B0h+var_350], 0ADh
0x1800384e3  mov     esi, 0Bh
0x1800384e8  mov     [rsp+3B0h+var_34C], esi
0x1800384ec  mov     [rsp+3B0h+var_348], 0FFh
0x1800384f4  mov     [rbp+2B0h+var_2C8], 1000000h
0x1800384fb  xor     edx, edx; Val
0x1800384fd  lea     r8d, [rsi+6Dh]; Size
0x180038501  lea     rcx, [rsp+3B0h+var_340]; void *
0x180038506  call    memset_0
0x18003850b  xor     r8d, r8d
0x18003850e  lea     rdx, [rsp+3B0h+var_368]
0x180038513  lea     rcx, [rbp+2B0h+var_2C0]
0x180038517  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18003851c  nop
0x18003851d  mov     [rsp+3B0h+var_370], 0
0x180038526  lea     r9, [rbp+2B0h+arg_10]; char *
0x18003852d  mov     r8, [rbp+2B0h+arg_8]; unsigned __int16 *
0x180038534  lea     rcx, [rbp+2B0h+SubKey]; unsigned __int16 *
0x180038538  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x18003853d  mov     ebx, eax
0x18003853f  mov     [rbp+2B0h+var_2B8], eax
0x180038542  test    eax, eax
0x180038544  js      loc_180038672
0x18003854a  lea     rdx, [rbp+2B0h+SubKey]; lpSubKey
0x18003854e  mov     rcx, [rdi+8]; hKey
0x180038552  call    cs:__imp_RegDeleteTreeW
0x180038558  mov     ebx, eax
0x18003855a  cmp     eax, 2
0x18003855d  jnz     short loc_1800385C7
0x18003855f  mov     [rsp+3B0h+var_368], r15
0x180038564  mov     [rsp+3B0h+var_360], r12
0x180038569  mov     qword ptr [rsp+3B0h+var_358], r13
0x18003856e  mov     [rsp+3B0h+var_350], 0C0h
0x180038576  mov     [rsp+3B0h+var_34C], esi
0x18003857a  mov     [rsp+3B0h+var_348], 0FFh
0x180038582  mov     [rbp+2B0h+var_2C8], 1000000h
0x180038589  xor     edx, edx; Val
0x18003858b  lea     r8d, [rsi+6Dh]; Size
0x18003858f  lea     rcx, [rsp+3B0h+var_340]; void *
0x180038594  call    memset_0
0x180038599  lea     rax, [rbp+2B0h+SubKey]
0x18003859d  mov     [rsp+3B0h+var_388], rax
0x1800385a2  mov     rax, [rdi+18h]
0x1800385a6  mov     [rsp+3B0h+var_390], rax
0x1800385ab  lea     r9, aKeyWithPathSSN; "Key with path %s\\%s not found"
0x1800385b2  mov     r8d, 80042308h
0x1800385b8  lea     rdx, [rsp+3B0h+var_368]
0x1800385bd  lea     rcx, [rbp+2B0h+var_2C0]
0x1800385c1  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x1800385c7  test    eax, eax
0x1800385c9  jz      short loc_180038648
0x1800385cb  mov     rsi, [rdi+18h]
0x1800385cf  mov     rdi, [rdi+8]
0x1800385d3  jle     short loc_1800385DE
0x1800385d5  movzx   ebx, ax
0x1800385d8  or      ebx, 80070000h
0x1800385de  mov     [rsp+3B0h+var_368], r15
0x1800385e3  mov     [rsp+3B0h+var_360], r12
0x1800385e8  mov     qword ptr [rsp+3B0h+var_358], r13
0x1800385ed  mov     [rsp+3B0h+var_350], 0C3h
0x1800385f5  mov     [rsp+3B0h+var_34C], 0Bh
0x1800385fd  mov     [rsp+3B0h+var_348], 0FFh
0x180038605  mov     [rbp+2B0h+var_2C8], 1000000h
0x18003860c  xor     edx, edx; Val
0x18003860e  lea     r8d, [rdx+78h]; Size
0x180038612  lea     rcx, [rsp+3B0h+var_340]; void *
0x180038617  call    memset_0
0x18003861c  lea     rax, [rbp+2B0h+SubKey]
0x180038620  mov     [rsp+30h], rax
0x180038625  mov     [rsp+3B0h+var_388], rsi
0x18003862a  mov     [rsp+3B0h+var_390], rdi
0x18003862f  lea     r9, aShdeletekeyLdS; "SHDeleteKey(%ld[%s],%s)"
0x180038636  mov     r8d, ebx
0x180038639  lea     rdx, [rsp+3B0h+var_368]
0x18003863e  lea     rcx, [rbp+2B0h+var_2C0]
0x180038642  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x180038648  lea     rcx, [rbp+2B0h+var_2C0]; this
0x18003864c  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x180038651  mov     rcx, [rbp+2B0h+var_40]
0x180038658  xor     rcx, rsp; StackCookie
0x18003865b  call    __security_check_cookie
0x180038660  add     rsp, 380h
0x180038667  pop     r15
0x180038669  pop     r13
0x18003866b  pop     r12
0x18003866d  pop     rdi
0x18003866e  pop     rsi
0x18003866f  pop     rbx
0x180038670  pop     rbp
0x180038671  retn
0x180038672  mov     [rsp+3B0h+var_368], r15
0x180038677  mov     [rsp+3B0h+var_360], r12
0x18003867c  mov     qword ptr [rsp+3B0h+var_358], r13
0x180038681  mov     [rsp+3B0h+var_350], 0B8h
0x180038689  mov     [rsp+3B0h+var_34C], esi
0x18003868d  mov     [rsp+3B0h+var_348], 0FFh
0x180038695  mov     [rbp+2B0h+var_2C8], 1000000h
0x18003869c  xor     edx, edx; Val
0x18003869e  lea     r8d, [rdx+78h]; Size
0x1800386a2  lea     rcx, [rsp+3B0h+var_340]; void *
0x1800386a7  call    memset_0
0x1800386ac  lea     r9, aStringcchvprin; "StringCchVPrintfW()"
0x1800386b3  mov     r8d, ebx
0x1800386b6  lea     rdx, [rsp+3B0h+var_368]
0x1800386bb  lea     rcx, [rbp+2B0h+var_2C0]
0x1800386bf  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
```
