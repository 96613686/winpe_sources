# SamLookupNamesInDomain

- ea: `0x1800038b0`
- end: `0x1800039f6`
- name: `SamLookupNamesInDomain`
- size: `326`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _UNICODE_STRING *, unsigned int **, enum _SID_NAME_USE **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000918c`

## callees

- `0x1800038b0`
- `0x180003a00`
- `0x1800078c0`
- `0x18000807c`
- `0x18000ba10`
- `0x18000c070`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003917`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003917`

## pseudocode

```c
__int64 __fastcall SamLookupNamesInDomain(
        void **a1,
        unsigned int a2,
        struct _UNICODE_STRING *a3,
        unsigned int **a4,
        enum _SID_NAME_USE **a5)
{
  unsigned __int16 *CallingProcessInfo; // rax
  __int64 v10; // rcx
  unsigned __int16 *v11; // r14
  const wchar_t *v12; // r9
  int v13; // eax
  unsigned int v14; // ebx
  PVOID v15; // rcx

  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
  {
    CallingProcessInfo = SampQueryCallingProcessInfo();
    v11 = CallingProcessInfo;
    if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    {
      v12 = L"<unknown>";
      if ( CallingProcessInfo )
        v12 = CallingProcessInfo;
      McTemplateU0pqz_EventWriteTransfer(
        v10,
        (const EVENT_DESCRIPTOR *)SamLookupNamesInDomainEntry,
        (__int64)a1,
        a2,
        v12);
    }
    LocalFree(v11);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
  v13 = SamiLookupNamesInDomain(a1, 1, a2, a3, a4, a5);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        103,
        &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
        (unsigned int)v13);
  }
  else
  {
    v15 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
  }
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    McTemplateU0d_EventWriteTransfer((__int64)v15, (const EVENT_DESCRIPTOR *)SamLookupNamesInDomainExit, v14);
  return v14;
}

```

## disassembly

```asm
0x1800038b0  push    rbx
0x1800038b2  sub     rsp, 30h
0x1800038b6  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800038bd  mov     ebx, edx
0x1800038bf  mov     [rsp+38h+arg_0], rbp
0x1800038c4  mov     rbp, r8
0x1800038c7  mov     [rsp+38h+arg_8], rsi
0x1800038cc  mov     rsi, r9
0x1800038cf  mov     [rsp+38h+arg_10], rdi
0x1800038d4  mov     rdi, rcx
0x1800038d7  jz      short loc_180003922
0x1800038d9  mov     [rsp+38h+arg_18], r14
0x1800038de  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x1800038e3  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800038ea  mov     r14, rax
0x1800038ed  jz      short loc_180003914
0x1800038ef  test    rax, rax
0x1800038f2  lea     r9, aUnknown; "<unknown>"
0x1800038f9  mov     r8, rdi
0x1800038fc  lea     rdx, SamLookupNamesInDomainEntry
0x180003903  cmovnz  r9, rax
0x180003907  mov     [rsp+38h+var_18], r9
0x18000390c  mov     r9d, ebx
0x18000390f  call    McTemplateU0pqz_EventWriteTransfer
0x180003914  mov     rcx, r14; hMem
0x180003917  call    cs:__imp_LocalFree
0x18000391d  mov     r14, [rsp+38h+arg_18]
0x180003922  mov     rcx, cs:WPP_GLOBAL_Control
0x180003929  test    byte ptr [rcx+1Ch], 2
0x18000392d  jz      short loc_18000394A
0x18000392f  cmp     byte ptr [rcx+19h], 4
0x180003933  jb      short loc_18000394A
0x180003935  mov     rcx, [rcx+10h]
0x180003939  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180003940  mov     edx, 65h ; 'e'
0x180003945  call    WPP_SF_
0x18000394a  mov     rax, [rsp+38h+arg_20]
0x18000394f  mov     r9, rbp; struct _UNICODE_STRING *
0x180003952  mov     [rsp+38h+var_10], rax; enum _SID_NAME_USE **
0x180003957  mov     r8d, ebx; unsigned int
0x18000395a  mov     edx, 1; unsigned int
0x18000395f  mov     [rsp+38h+var_18], rsi; unsigned int **
0x180003964  mov     rcx, rdi; void *
0x180003967  call    ?SamiLookupNamesInDomain@@YAJPEAXKKPEAU_UNICODE_STRING@@PEAPEAKPEAPEAW4_SID_NAME_USE@@@Z; SamiLookupNamesInDomain(void *,ulong,ulong,_UNICODE_STRING *,ulong * *,_SID_NAME_USE * *)
0x18000396c  mov     rdi, [rsp+38h+arg_10]
0x180003971  mov     ebx, eax
0x180003973  mov     rsi, [rsp+38h+arg_8]
0x180003978  mov     rbp, [rsp+38h+arg_0]
0x18000397d  test    eax, eax
0x18000397f  js      short loc_1800039AB
0x180003981  mov     rcx, cs:WPP_GLOBAL_Control
0x180003988  test    byte ptr [rcx+1Ch], 2
0x18000398c  jz      short loc_1800039D6
0x18000398e  cmp     byte ptr [rcx+19h], 4
0x180003992  jb      short loc_1800039D6
0x180003994  mov     rcx, [rcx+10h]
0x180003998  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000399f  mov     edx, 66h ; 'f'
0x1800039a4  call    WPP_SF_
0x1800039a9  jmp     short loc_1800039D6
0x1800039ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800039b2  test    byte ptr [rcx+1Ch], 2
0x1800039b6  jz      short loc_1800039D6
0x1800039b8  cmp     byte ptr [rcx+19h], 2
0x1800039bc  jb      short loc_1800039D6
0x1800039be  mov     rcx, [rcx+10h]
0x1800039c2  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x1800039c9  mov     edx, 67h ; 'g'
0x1800039ce  mov     r9d, ebx
0x1800039d1  call    WPP_SF_D
0x1800039d6  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x1800039dd  jz      short loc_1800039EE
0x1800039df  mov     r8d, ebx
0x1800039e2  lea     rdx, SamLookupNamesInDomainExit
0x1800039e9  call    McTemplateU0d_EventWriteTransfer
0x1800039ee  mov     eax, ebx
0x1800039f0  add     rsp, 30h
0x1800039f4  pop     rbx
0x1800039f5  retn
```
