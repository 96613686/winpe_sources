# CWinInetHelperClass::ReconfirmLowHealth(ulong,tagHypothesisResult *,ushort * *,tagDIAGNOSIS_STATUS *)

- ea: `0x18000b020`
- end: `0x18000b17f`
- name: `?ReconfirmLowHealth@CWinInetHelperClass@@UEAAJKPEAUtagHypothesisResult@@PEAPEAGPEAW4tagDIAGNOSIS_STATUS@@@Z`
- size: `351`
- prototype: `__int64 __fastcall(CWinInetHelperClass *__hidden this, unsigned int, struct tagHypothesisResult *, unsigned __int16 **, enum tagDIAGNOSIS_STATUS *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b020`
- `0x18000e7d0`
- `0x180012d6e`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b130`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b15f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b130`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b15f`

## string_xrefs

- `0x18000b067`: `Hypotheses path confirmed, will not return any repairs.`
- `0x18000b0fe`: `The failure may be due to WPAD cache. Cache contents cleared.`

## pseudocode

```c
__int64 __fastcall CWinInetHelperClass::ReconfirmLowHealth(
        CWinInetHelperClass *this,
        unsigned int a2,
        struct tagHypothesisResult *a3,
        unsigned __int16 **a4)
{
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rdi
  __int64 v8; // rcx
  void *v9; // rcx
  LPVOID pv; // [rsp+30h] [rbp-98h] BYREF
  int v12; // [rsp+38h] [rbp-90h]
  LPVOID v13; // [rsp+40h] [rbp-88h]
  void *v14; // [rsp+48h] [rbp-80h]

  v5 = 0;
  if ( a2 )
  {
    while ( a3[v5].pathStatus != DS_CONFIRMED )
    {
      v5 = (unsigned int)(v5 + 1);
      if ( (unsigned int)v5 >= a2 )
        goto LABEL_7;
    }
    v6 = *((_QWORD *)this + 595);
    *((_DWORD *)this + 1091) = 1;
    if ( v6 )
      (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v6 + 24LL))(
        v6,
        2,
        0,
        L"WinInetHelperClass",
        L"Hypotheses path confirmed, will not return any repairs.");
  }
LABEL_7:
  if ( *((_DWORD *)this + 1091) )
  {
    v7 = *((_QWORD *)this + 596);
    if ( v7 )
    {
      memset_0(&pv, 0, 0x90u);
      if ( (*(int (__fastcall **)(__int64, const wchar_t *, LPVOID *))(*(_QWORD *)v7 + 32LL))(
             v7,
             L"PossibleProxiedScenario",
             &pv) >= 0 )
      {
        if ( (_DWORD)v13 )
        {
          _RunAsImpersonatedUser(L"ForceProxyDetectionOnNextRun");
          v8 = *((_QWORD *)this + 595);
          if ( v8 )
            (*(void (__fastcall **)(__int64, __int64, _QWORD, const wchar_t *, const wchar_t *))(*(_QWORD *)v8 + 24LL))(
              v8,
              2,
              0,
              L"WinInetHelperClass",
              L"The failure may be due to WPAD cache. Cache contents cleared.");
          *((_DWORD *)this + 1226) = 1;
        }
        CoTaskMemFree(pv);
        pv = 0;
        if ( v12 == 10 )
        {
          v9 = v13;
          goto LABEL_18;
        }
        if ( v12 == 14 )
        {
          v9 = v14;
LABEL_18:
          CoTaskMemFree(v9);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000b020  mov     [rsp+arg_0], rbx
0x18000b025  push    rdi
0x18000b026  sub     rsp, 0C0h
0x18000b02d  mov     rbx, rcx
0x18000b030  mov     r9d, edx
0x18000b033  xor     ecx, ecx
0x18000b035  test    edx, edx
0x18000b037  jz      short loc_18000B08A
0x18000b039  lea     rdx, [rcx+rcx*4]
0x18000b03d  cmp     dword ptr [r8+rdx*8+20h], 1
0x18000b043  jz      short loc_18000B04E
0x18000b045  inc     ecx
0x18000b047  cmp     ecx, r9d
0x18000b04a  jb      short loc_18000B039
0x18000b04c  jmp     short loc_18000B08A
0x18000b04e  mov     rcx, [rbx+1298h]
0x18000b055  mov     dword ptr [rbx+110Ch], 1
0x18000b05f  test    rcx, rcx
0x18000b062  jz      short loc_18000B08A
0x18000b064  mov     rax, [rcx]
0x18000b067  lea     rdx, aHypothesesPath; "Hypotheses path confirmed, will not ret"...
0x18000b06e  xor     r8d, r8d
0x18000b071  mov     [rsp+0C8h+var_A8], rdx
0x18000b076  lea     r9, aWininethelperc; "WinInetHelperClass"
0x18000b07d  mov     rax, [rax+18h]
0x18000b081  lea     edx, [r8+2]
0x18000b085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b08a  cmp     dword ptr [rbx+110Ch], 0
0x18000b091  jz      loc_18000B16B
0x18000b097  mov     rdi, [rbx+12A0h]
0x18000b09e  test    rdi, rdi
0x18000b0a1  jz      loc_18000B16B
0x18000b0a7  xor     edx, edx; Val
0x18000b0a9  lea     rcx, [rsp+0C8h+pv]; void *
0x18000b0ae  mov     r8d, 90h; Size
0x18000b0b4  call    memset_0
0x18000b0b9  mov     rax, [rdi]
0x18000b0bc  lea     r8, [rsp+0C8h+pv]
0x18000b0c1  lea     rdx, aPossibleproxie; "PossibleProxiedScenario"
0x18000b0c8  mov     rcx, rdi
0x18000b0cb  mov     rax, [rax+20h]
0x18000b0cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b0d4  test    eax, eax
0x18000b0d6  js      loc_18000B16B
0x18000b0dc  cmp     dword ptr [rsp+0C8h+var_88], 0
0x18000b0e1  jz      short loc_18000B12B
0x18000b0e3  lea     rcx, aForceproxydete_0; "ForceProxyDetectionOnNextRun"
0x18000b0ea  call    ?_RunAsImpersonatedUser@@YAJPEBG@Z; _RunAsImpersonatedUser(ushort const *)
0x18000b0ef  mov     rcx, [rbx+1298h]
0x18000b0f6  test    rcx, rcx
0x18000b0f9  jz      short loc_18000B121
0x18000b0fb  mov     rax, [rcx]
0x18000b0fe  lea     r10, aTheFailureMayB; "The failure may be due to WPAD cache. C"...
0x18000b105  xor     r8d, r8d
0x18000b108  mov     [rsp+0C8h+var_A8], r10
0x18000b10d  lea     r9, aWininethelperc; "WinInetHelperClass"
0x18000b114  mov     rax, [rax+18h]
0x18000b118  lea     edx, [r8+2]
0x18000b11c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b121  mov     dword ptr [rbx+1328h], 1
0x18000b12b  mov     rcx, [rsp+0C8h+pv]; pv
0x18000b130  call    cs:__imp_CoTaskMemFree
0x18000b137  nop     dword ptr [rax+rax+00h]
0x18000b13c  cmp     [rsp+0C8h+var_90], 0Ah
0x18000b141  mov     [rsp+0C8h+pv], 0
0x18000b14a  jz      short loc_18000B15A
0x18000b14c  cmp     [rsp+0C8h+var_90], 0Eh
0x18000b151  jnz     short loc_18000B16B
0x18000b153  mov     rcx, [rsp+0C8h+var_80]
0x18000b158  jmp     short loc_18000B15F
0x18000b15a  mov     rcx, [rsp+0C8h+var_88]; pv
0x18000b15f  call    cs:__imp_CoTaskMemFree
0x18000b166  nop     dword ptr [rax+rax+00h]
0x18000b16b  mov     rbx, [rsp+0C8h+arg_0]
0x18000b173  xor     eax, eax
0x18000b175  add     rsp, 0C0h
0x18000b17c  pop     rdi
0x18000b17d  retn
```
