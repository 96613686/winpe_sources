# SamLookupNamesInDomain2

- ea: `0x180003760`
- end: `0x1800038a6`
- name: `SamLookupNamesInDomain2`
- size: `326`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _UNICODE_STRING *, unsigned int **, enum _SID_NAME_USE **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003760`
- `0x180003a00`
- `0x1800078c0`
- `0x18000807c`
- `0x18000ba10`
- `0x18000c070`
- `0x1800160d8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800037c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800037c7`

## pseudocode

```c
__int64 __fastcall SamLookupNamesInDomain2(
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
        (const EVENT_DESCRIPTOR *)SamLookupNamesInDomain2Entry,
        (__int64)a1,
        a2,
        v12);
    }
    LocalFree(v11);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
  v13 = SamiLookupNamesInDomain(a1, 2, a2, a3, a4, a5);
  v14 = v13;
  if ( v13 < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        106,
        &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids,
        (unsigned int)v13);
  }
  else
  {
    v15 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids);
  }
  if ( (Microsoft_Windows_SAMLIBEnableBits & 1) != 0 )
    McTemplateU0d_EventWriteTransfer((__int64)v15, (const EVENT_DESCRIPTOR *)SamLookupNamesInDomain2Exit, v14);
  return v14;
}

```

## disassembly

```asm
0x180003760  push    rbx
0x180003762  sub     rsp, 30h
0x180003766  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000376d  mov     ebx, edx
0x18000376f  mov     [rsp+38h+arg_0], rbp
0x180003774  mov     rbp, r8
0x180003777  mov     [rsp+38h+arg_8], rsi
0x18000377c  mov     rsi, r9
0x18000377f  mov     [rsp+38h+arg_10], rdi
0x180003784  mov     rdi, rcx
0x180003787  jz      short loc_1800037D2
0x180003789  mov     [rsp+38h+arg_18], r14
0x18000378e  call    ?SampQueryCallingProcessInfo@@YAPEAGXZ; SampQueryCallingProcessInfo(void)
0x180003793  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000379a  mov     r14, rax
0x18000379d  jz      short loc_1800037C4
0x18000379f  test    rax, rax
0x1800037a2  lea     r9, aUnknown; "<unknown>"
0x1800037a9  mov     r8, rdi
0x1800037ac  lea     rdx, SamLookupNamesInDomain2Entry
0x1800037b3  cmovnz  r9, rax
0x1800037b7  mov     [rsp+38h+var_18], r9
0x1800037bc  mov     r9d, ebx
0x1800037bf  call    McTemplateU0pqz_EventWriteTransfer
0x1800037c4  mov     rcx, r14; hMem
0x1800037c7  call    cs:__imp_LocalFree
0x1800037cd  mov     r14, [rsp+38h+arg_18]
0x1800037d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037d9  test    byte ptr [rcx+1Ch], 2
0x1800037dd  jz      short loc_1800037FA
0x1800037df  cmp     byte ptr [rcx+19h], 4
0x1800037e3  jb      short loc_1800037FA
0x1800037e5  mov     rcx, [rcx+10h]
0x1800037e9  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x1800037f0  mov     edx, 68h ; 'h'
0x1800037f5  call    WPP_SF_
0x1800037fa  mov     rax, [rsp+38h+arg_20]
0x1800037ff  mov     r9, rbp; struct _UNICODE_STRING *
0x180003802  mov     [rsp+38h+var_10], rax; enum _SID_NAME_USE **
0x180003807  mov     r8d, ebx; unsigned int
0x18000380a  mov     edx, 2; unsigned int
0x18000380f  mov     [rsp+38h+var_18], rsi; unsigned int **
0x180003814  mov     rcx, rdi; void *
0x180003817  call    ?SamiLookupNamesInDomain@@YAJPEAXKKPEAU_UNICODE_STRING@@PEAPEAKPEAPEAW4_SID_NAME_USE@@@Z; SamiLookupNamesInDomain(void *,ulong,ulong,_UNICODE_STRING *,ulong * *,_SID_NAME_USE * *)
0x18000381c  mov     rdi, [rsp+38h+arg_10]
0x180003821  mov     ebx, eax
0x180003823  mov     rsi, [rsp+38h+arg_8]
0x180003828  mov     rbp, [rsp+38h+arg_0]
0x18000382d  test    eax, eax
0x18000382f  js      short loc_18000385B
0x180003831  mov     rcx, cs:WPP_GLOBAL_Control
0x180003838  test    byte ptr [rcx+1Ch], 2
0x18000383c  jz      short loc_180003886
0x18000383e  cmp     byte ptr [rcx+19h], 4
0x180003842  jb      short loc_180003886
0x180003844  mov     rcx, [rcx+10h]
0x180003848  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x18000384f  mov     edx, 69h ; 'i'
0x180003854  call    WPP_SF_
0x180003859  jmp     short loc_180003886
0x18000385b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003862  test    byte ptr [rcx+1Ch], 2
0x180003866  jz      short loc_180003886
0x180003868  cmp     byte ptr [rcx+19h], 2
0x18000386c  jb      short loc_180003886
0x18000386e  mov     rcx, [rcx+10h]
0x180003872  lea     r8, WPP_d8484c4e18fe38141931591e4d8996d6_Traceguids
0x180003879  mov     edx, 6Ah ; 'j'
0x18000387e  mov     r9d, ebx
0x180003881  call    WPP_SF_D
0x180003886  test    byte ptr cs:Microsoft_Windows_SAMLIBEnableBits, 1
0x18000388d  jz      short loc_18000389E
0x18000388f  mov     r8d, ebx
0x180003892  lea     rdx, SamLookupNamesInDomain2Exit
0x180003899  call    McTemplateU0d_EventWriteTransfer
0x18000389e  mov     eax, ebx
0x1800038a0  add     rsp, 30h
0x1800038a4  pop     rbx
0x1800038a5  retn
```
