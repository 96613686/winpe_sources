# TpmSWAntiHammeringMgr::WriteUserAuthFailureData(TpmUserAuthFailureData *)

- ea: `0x1400222b8`
- end: `0x140022438`
- name: `?WriteUserAuthFailureData@TpmSWAntiHammeringMgr@@AEAAJPEAVTpmUserAuthFailureData@@@Z`
- size: `384`
- prototype: `__int64 __fastcall(TpmSWAntiHammeringMgr *__hidden this, struct TpmUserAuthFailureData *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14001a3a0`
- `0x140022270`
- `0x140022440`

## callees

- `0x14000b9a4`
- `0x1400222b8`
- `0x14002f7a4`
- `0x14002fc8c`
- `0x14002fd1c`
- `0x14003005c`
- `0x140039740`
- `0x14004eb48`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002240e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002240e`

## string_xrefs

- `0x1400222f8`: `\Registry\Machine\System\CurrentControlSet\Services\TPM\AuthorizationFailure`

## pseudocode

```c
__int64 __fastcall TpmSWAntiHammeringMgr::WriteUserAuthFailureData(
        TpmSWAntiHammeringMgr *this,
        struct TpmUserAuthFailureData *a2)
{
  __int64 v3; // rax
  __int64 v4; // rdx
  NTSTATUS Key; // ebx
  int v6; // edi
  PVOID P; // [rsp+30h] [rbp-D0h] BYREF
  int v9; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v10[2]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v11[2]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v12[2]; // [rsp+70h] [rbp-90h]
  wchar_t pszDest[336]; // [rsp+90h] [rbp-70h] BYREF

  v10[1] = v11;
  v3 = *(_QWORD *)a2;
  v11[0] = *(_OWORD *)L"D:(A;;GA;;;SY)(A;;GA;;;BA)";
  v10[0] = 3538996;
  v11[1] = *(_OWORD *)L";;;SY)(A;;GA;;;BA)";
  P = 0;
  v12[0] = *(_OWORD *)L";;GA;;;BA)";
  *(_QWORD *)((char *)v12 + 14) = *(_QWORD *)L"BA)";
  Key = RtlStringCchPrintfW(
          pszDest,
          0x14Eu,
          L"%s\\%s",
          L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\TPM\\AuthorizationFailure",
          v3);
  if ( Key >= 0 )
  {
    v6 = *((_DWORD *)a2 + 5);
    if ( v6 )
    {
      Key = SeSddlSecurityDescriptorFromSDDL(v10, v4, &P);
      if ( Key >= 0 )
      {
        Key = TpmRegistry::CreateKey(19, P);
        if ( Key >= 0 )
        {
          Key = TpmRegistry::CreateKey(pszDest, P);
          if ( Key >= 0 )
          {
            v9 = v6;
            Key = TpmRegistry::AssignValue(pszDest, L"Count", 4u, &v9, 4u);
            if ( Key >= 0 )
              Key = TpmRegistry::AssignValue(pszDest, L"History", 3u, *((void **)a2 + 1), 8 * v6);
          }
        }
      }
    }
    else
    {
      TpmRegistry::DeleteKey(pszDest, v4);
      Key = 0;
    }
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x1400222b8  push    rbp
0x1400222ba  push    rbx
0x1400222bb  push    rsi
0x1400222bc  push    rdi
0x1400222bd  lea     rbp, [rsp-248h]
0x1400222c5  sub     rsp, 348h
0x1400222cc  mov     rax, cs:__security_cookie
0x1400222d3  xor     rax, rsp
0x1400222d6  mov     [rbp+260h+var_30], rax
0x1400222dd  movups  xmm0, xmmword ptr cs:aDAGaSyAGaBa; "D:(A;;GA;;;SY)(A;;GA;;;BA)"
0x1400222e4  lea     rax, [rsp+360h+var_310]
0x1400222e9  mov     rsi, rdx
0x1400222ec  movups  xmm1, xmmword ptr cs:aDAGaSyAGaBa+10h; ";;;SY)(A;;GA;;;BA)"
0x1400222f3  mov     [rsp+360h+var_318], rax
0x1400222f8  lea     r9, aRegistryMachin_18; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400222ff  mov     rax, [rdx]
0x140022302  lea     r8, aSS; "%s\\%s"
0x140022309  movups  [rsp+360h+var_310], xmm0
0x14002230e  mov     edx, 14Eh; cchDest
0x140022313  lea     rcx, [rbp+260h+pszDest]; pszDest
0x140022317  movups  xmm0, xmmword ptr cs:aDAGaSyAGaBa+20h; ";;GA;;;BA)"
0x14002231e  mov     [rsp+360h+var_320], 360034h
0x140022327  movups  [rsp+360h+var_300], xmm1
0x14002232c  mov     [rsp+360h+P], 0
0x140022335  movsd   xmm1, qword ptr cs:aDAGaSyAGaBa+2Eh; "BA)"
0x14002233d  movups  xmmword ptr [rsp+360h+var_2F0], xmm0
0x140022342  mov     qword ptr [rsp+360h+var_340], rax
0x140022347  movsd   qword ptr [rsp+360h+var_2F0+0Eh], xmm1
0x14002234d  call    RtlStringCchPrintfW
0x140022352  mov     ebx, eax
0x140022354  test    eax, eax
0x140022356  js      loc_140022402
0x14002235c  mov     edi, [rsi+14h]
0x14002235f  test    edi, edi
0x140022361  jnz     short loc_140022373
0x140022363  lea     rcx, [rbp+260h+pszDest]; unsigned __int16 *
0x140022367  call    ?DeleteKey@TpmRegistry@@SAJPEBGH@Z; TpmRegistry::DeleteKey(ushort const *,int)
0x14002236c  xor     ebx, ebx
0x14002236e  jmp     loc_140022402
0x140022373  lea     r8, [rsp+360h+P]
0x140022378  lea     rcx, [rsp+360h+var_320]
0x14002237d  call    SeSddlSecurityDescriptorFromSDDL
0x140022382  mov     ebx, eax
0x140022384  test    eax, eax
0x140022386  js      short loc_140022402
0x140022388  mov     rdx, [rsp+360h+P]
0x14002238d  mov     ecx, 13h
0x140022392  call    ?CreateKey@TpmRegistry@@SAJW4KEY_VALUES@1@PEAX@Z; TpmRegistry::CreateKey(TpmRegistry::KEY_VALUES,void *)
0x140022397  mov     ebx, eax
0x140022399  test    eax, eax
0x14002239b  js      short loc_140022402
0x14002239d  mov     rdx, [rsp+360h+P]; void *
0x1400223a2  lea     rcx, [rbp+260h+pszDest]; unsigned __int16 *
0x1400223a6  call    ?CreateKey@TpmRegistry@@SAJPEBGPEAX@Z; TpmRegistry::CreateKey(ushort const *,void *)
0x1400223ab  mov     ebx, eax
0x1400223ad  test    eax, eax
0x1400223af  js      short loc_140022402
0x1400223b1  mov     r8d, 4; unsigned int
0x1400223b7  mov     [rsp+360h+var_328], edi
0x1400223bb  lea     r9, [rsp+360h+var_328]; void *
0x1400223c0  mov     [rsp+360h+var_340], r8d; unsigned int
0x1400223c5  lea     rdx, aCount; "Count"
0x1400223cc  lea     rcx, [rbp+260h+pszDest]; unsigned __int16 *
0x1400223d0  call    ?AssignValue@TpmRegistry@@SAJPEBG0KPEAXK@Z; TpmRegistry::AssignValue(ushort const *,ushort const *,ulong,void *,ulong)
0x1400223d5  mov     ebx, eax
0x1400223d7  test    eax, eax
0x1400223d9  js      short loc_140022402
0x1400223db  mov     r9, [rsi+8]; void *
0x1400223df  lea     eax, ds:0[rdi*8]
0x1400223e6  mov     r8d, 3; unsigned int
0x1400223ec  mov     [rsp+360h+var_340], eax; unsigned int
0x1400223f0  lea     rdx, aHistory; "History"
0x1400223f7  lea     rcx, [rbp+260h+pszDest]; unsigned __int16 *
0x1400223fb  call    ?AssignValue@TpmRegistry@@SAJPEBG0KPEAXK@Z; TpmRegistry::AssignValue(ushort const *,ushort const *,ulong,void *,ulong)
0x140022400  mov     ebx, eax
0x140022402  mov     rcx, [rsp+360h+P]; P
0x140022407  test    rcx, rcx
0x14002240a  jz      short loc_14002241A
0x14002240c  xor     edx, edx; Tag
0x14002240e  call    cs:__imp_ExFreePoolWithTag
0x140022415  nop     dword ptr [rax+rax+00h]
0x14002241a  mov     eax, ebx
0x14002241c  mov     rcx, [rbp+260h+var_30]
0x140022423  xor     rcx, rsp; StackCookie
0x140022426  call    __security_check_cookie
0x14002242b  add     rsp, 348h
0x140022432  pop     rdi
0x140022433  pop     rsi
0x140022434  pop     rbx
0x140022435  pop     rbp
0x140022436  retn
```
