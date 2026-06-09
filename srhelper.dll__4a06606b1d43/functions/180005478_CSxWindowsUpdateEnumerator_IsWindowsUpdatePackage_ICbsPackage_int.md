# CSxWindowsUpdateEnumerator::_IsWindowsUpdatePackage(ICbsPackage *,int *)

- ea: `0x180005478`
- end: `0x18000559e`
- name: `?_IsWindowsUpdatePackage@CSxWindowsUpdateEnumerator@@CAJPEAUICbsPackage@@PEAH@Z`
- size: `294`
- prototype: `__int64 __fastcall(struct ICbsPackage *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x18000408c`

## callees

- `0x180003ce0`
- `0x180005478`
- `0x18000d348`
- `0x18000d43c`
- `0x180016010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180005546`
- `msvcrt!_wcsicmp` at `0x180005546`
- `ole32!CoTaskMemFree` at `0x180005570`
- `ole32!CoTaskMemFree` at `0x180005570`

## string_xrefs

- `0x1800054c7`: `CSxWindowsUpdateEnumerator::_IsWindowsUpdatePackage`

## pseudocode

```c
__int64 __fastcall CSxWindowsUpdateEnumerator::_IsWindowsUpdatePackage(struct ICbsPackage *a1, int *a2)
{
  __int16 v4; // ax
  __int64 v5; // rax
  __int64 v6; // rbx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  int v11; // [rsp+20h] [rbp-40h] BYREF
  __int16 v12; // [rsp+24h] [rbp-3Ch]
  __int16 v13; // [rsp+26h] [rbp-3Ah]
  wchar_t *String2; // [rsp+78h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&v11,
    "CSxWindowsUpdateEnumerator::_IsWindowsUpdatePackage",
    484);
  String2 = 0;
  v4 = 487;
  if ( !a2 || (v12 = 487, v4 = 488, !a1) )
  {
    v11 = -2147024809;
    goto LABEL_14;
  }
  v12 = 488;
  v5 = *(_QWORD *)a1;
  v11 = 0;
  *a2 = 0;
  v11 = (*(__int64 (__fastcall **)(struct ICbsPackage *, __int64, wchar_t **))(v5 + 32))(a1, 8, &String2);
  v4 = 492;
  if ( v11 < 0 )
  {
LABEL_14:
    v13 = v4;
    goto LABEL_15;
  }
  v12 = 492;
  v6 = 0;
  while ( !String2
       || _wcsicmp((const wchar_t *)(&CSxWindowsUpdateEnumerator::s_wszWindowsUpdateReleaseType)[v6], String2) )
  {
    v6 = (unsigned int)(v6 + 1);
    if ( (unsigned int)v6 >= 8 )
      goto LABEL_15;
  }
  *a2 = 1;
LABEL_15:
  CoTaskMemFree(String2);
  String2 = 0;
  v7 = v11;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v11, v8, v9);
  return v7;
}

```

## disassembly

```asm
0x180005478  mov     [rsp-8+arg_0], rbx
0x18000547d  mov     [rsp-8+arg_10], rdi
0x180005482  push    rbp
0x180005483  mov     rbp, rsp
0x180005486  sub     rsp, 60h
0x18000548a  mov     rdi, rdx
0x18000548d  mov     rbx, rcx
0x180005490  mov     rcx, cs:WPP_GLOBAL_Control
0x180005497  lea     rax, WPP_GLOBAL_Control
0x18000549e  cmp     rcx, rax
0x1800054a1  jz      short loc_1800054C1
0x1800054a3  test    dword ptr [rcx+1Ch], 20000000h
0x1800054aa  jz      short loc_1800054C1
0x1800054ac  mov     rcx, [rcx+10h]
0x1800054b0  lea     r8, WPP_012e94a410f034635dd5ee797f3d6253_Traceguids
0x1800054b7  mov     edx, 11h
0x1800054bc  call    WPP_SF_
0x1800054c1  mov     r8d, 1E4h; unsigned __int16
0x1800054c7  lea     rdx, aCsxwindowsupda_1; "CSxWindowsUpdateEnumerator::_IsWindowsU"...
0x1800054ce  lea     rcx, [rbp+var_40]; this
0x1800054d2  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800054d7  mov     [rbp+String2], 0
0x1800054df  mov     eax, 1E7h
0x1800054e4  test    rdi, rdi
0x1800054e7  jz      short loc_180005561
0x1800054e9  mov     [rbp+var_3C], ax
0x1800054ed  mov     eax, 1E8h
0x1800054f2  test    rbx, rbx
0x1800054f5  jz      short loc_180005561
0x1800054f7  mov     [rbp+var_3C], ax
0x1800054fb  lea     r8, [rbp+String2]
0x1800054ff  mov     rax, [rbx]
0x180005502  mov     edx, 8
0x180005507  mov     rcx, rbx
0x18000550a  mov     [rbp+var_40], 0
0x180005511  mov     dword ptr [rdi], 0
0x180005517  mov     rax, [rax+20h]
0x18000551b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005520  mov     [rbp+var_40], eax
0x180005523  test    eax, eax
0x180005525  mov     eax, 1ECh
0x18000552a  js      short loc_180005568
0x18000552c  mov     [rbp+var_3C], ax
0x180005530  xor     ebx, ebx
0x180005532  mov     rdx, [rbp+String2]; String2
0x180005536  test    rdx, rdx
0x180005539  jz      short loc_180005550
0x18000553b  lea     rax, ?s_wszWindowsUpdateReleaseType@CSxWindowsUpdateEnumerator@@0PAPEBGA; ushort const * near * CSxWindowsUpdateEnumerator::s_wszWindowsUpdateReleaseType
0x180005542  mov     rcx, [rax+rbx*8]; String1
0x180005546  call    cs:__imp__wcsicmp
0x18000554c  test    eax, eax
0x18000554e  jz      short loc_180005559
0x180005550  inc     ebx
0x180005552  cmp     ebx, 8
0x180005555  jb      short loc_180005532
0x180005557  jmp     short loc_18000556C
0x180005559  mov     dword ptr [rdi], 1
0x18000555f  jmp     short loc_18000556C
0x180005561  mov     [rbp+var_40], 80070057h
0x180005568  mov     [rbp+var_3A], ax
0x18000556c  mov     rcx, [rbp+String2]; pv
0x180005570  call    cs:__imp_CoTaskMemFree
0x180005576  mov     [rbp+String2], 0
0x18000557e  mov     ebx, [rbp+var_40]
0x180005581  lea     rcx, [rbp+var_40]; this
0x180005585  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000558a  lea     r11, [rsp+60h+var_s0]
0x18000558f  mov     eax, ebx
0x180005591  mov     rbx, [r11+10h]
0x180005595  mov     rdi, [r11+20h]
0x180005599  mov     rsp, r11
0x18000559c  pop     rbp
0x18000559d  retn
```
