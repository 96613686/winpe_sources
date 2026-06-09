# CSdAsync::GetNetworkUserStringSid(ushort * *)

- ea: `0x180056d60`
- end: `0x180056efd`
- name: `?GetNetworkUserStringSid@CSdAsync@@UEAAJPEAPEAG@Z`
- size: `413`
- prototype: `__int64 __fastcall(CSdAsync *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180009d44`
- `0x180056d60`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180056ec9`
- `KERNEL32!LocalFree` at `0x180056ec9`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180056ddb`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180056ddb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180056e0f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180056e0f`
- `ole32!CoTaskMemFree` at `0x180056eb4`
- `ole32!CoTaskMemFree` at `0x180056eb4`
- `ole32!CoTaskMemAlloc` at `0x180056e55`
- `ole32!CoTaskMemAlloc` at `0x180056e55`

## string_xrefs

- `0x180056d87`: `CSdAsync::GetNetworkUserStringSid`

## pseudocode

```c
__int64 __fastcall CSdAsync::GetNetworkUserStringSid(CSdAsync *this, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rbx
  __int16 v5; // ax
  void *v6; // rcx
  bool v7; // zf
  __int64 v8; // rcx
  __int64 v9; // rax
  unsigned __int64 v10; // rsi
  unsigned int v11; // ebx
  int LastFailureAsHRESULT; // [rsp+20h] [rbp-40h] BYREF
  __int16 v14; // [rsp+24h] [rbp-3Ch]
  __int16 v15; // [rsp+26h] [rbp-3Ah]
  LPWSTR StringSid; // [rsp+88h] [rbp+28h] BYREF

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CSdAsync::GetNetworkUserStringSid",
    0x52Au,
    1u);
  StringSid = 0;
  v4 = 0;
  v5 = 1330;
  if ( a2 )
  {
    *a2 = 0;
    LastFailureAsHRESULT = 0;
    v14 = 1330;
    v6 = (void *)*((_QWORD *)this + 35);
    if ( !v6 )
    {
      LastFailureAsHRESULT = 1;
      v14 = 1334;
      goto LABEL_16;
    }
    v7 = !IsValidSid(v6);
    v5 = 1337;
    if ( v7 )
    {
      LastFailureAsHRESULT = -2147467259;
    }
    else
    {
      LastFailureAsHRESULT = 0;
      v14 = 1337;
      if ( ConvertSidToStringSidW(*((PSID *)this + 35), &StringSid) )
      {
        LastFailureAsHRESULT = 0;
        v14 = 1338;
        v9 = -1;
        do
          ++v9;
        while ( StringSid[v9] );
        v10 = (unsigned int)(v9 + 1);
        v4 = (unsigned __int16 *)CoTaskMemAlloc(2 * v10);
        v5 = 1342;
        if ( v4 )
        {
          LastFailureAsHRESULT = 0;
          v14 = 1342;
          LastFailureAsHRESULT = StringCchCopyW(v4, v10, StringSid);
          v5 = 1343;
          if ( LastFailureAsHRESULT >= 0 )
          {
            v14 = 1343;
            *a2 = v4;
            v4 = 0;
            goto LABEL_16;
          }
        }
        else
        {
          LastFailureAsHRESULT = -2147024882;
        }
      }
      else
      {
        LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
        v5 = 1338;
      }
    }
  }
  else
  {
    LastFailureAsHRESULT = -2147024809;
  }
  v15 = v5;
LABEL_16:
  CoTaskMemFree(v4);
  if ( StringSid )
  {
    LocalFree(StringSid);
    StringSid = 0;
  }
  v11 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v11;
}

```

## disassembly

```asm
0x180056d60  mov     [rsp-18h+arg_0], rbx
0x180056d65  mov     [rsp-18h+arg_10], rsi
0x180056d6a  push    rbp
0x180056d6b  push    rdi
0x180056d6c  push    r14
0x180056d6e  mov     rbp, rsp
0x180056d71  sub     rsp, 60h
0x180056d75  mov     rdi, rdx
0x180056d78  mov     rsi, rcx
0x180056d7b  mov     r9d, 1; unsigned __int16
0x180056d81  mov     r8d, 52Ah; unsigned __int16
0x180056d87  lea     rdx, aCsdasyncGetnet; "CSdAsync::GetNetworkUserStringSid"
0x180056d8e  lea     rcx, [rbp+var_40]; this
0x180056d92  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180056d97  xor     r14d, r14d
0x180056d9a  mov     [rbp+StringSid], r14
0x180056d9e  mov     ebx, r14d
0x180056da1  mov     eax, 532h
0x180056da6  test    rdi, rdi
0x180056da9  jz      loc_180056EA6
0x180056daf  mov     [rdi], r14
0x180056db2  mov     [rbp+var_40], r14d
0x180056db6  mov     [rbp+var_3C], ax
0x180056dba  mov     rcx, [rsi+118h]; pSid
0x180056dc1  test    rcx, rcx
0x180056dc4  jnz     short loc_180056DDB
0x180056dc6  mov     [rbp+var_40], 1
0x180056dcd  mov     eax, 536h
0x180056dd2  mov     [rbp+var_3C], ax
0x180056dd6  jmp     loc_180056EB1
0x180056ddb  call    cs:__imp_IsValidSid
0x180056de2  nop     dword ptr [rax+rax+00h]
0x180056de7  test    eax, eax
0x180056de9  mov     eax, 539h
0x180056dee  jnz     short loc_180056DFC
0x180056df0  mov     [rbp+var_40], 80004005h
0x180056df7  jmp     loc_180056EAD
0x180056dfc  mov     [rbp+var_40], r14d
0x180056e00  mov     [rbp+var_3C], ax
0x180056e04  lea     rdx, [rbp+StringSid]; StringSid
0x180056e08  mov     rcx, [rsi+118h]; Sid
0x180056e0f  call    cs:__imp_ConvertSidToStringSidW
0x180056e16  nop     dword ptr [rax+rax+00h]
0x180056e1b  test    eax, eax
0x180056e1d  jnz     short loc_180056E2E
0x180056e1f  call    GetLastFailureAsHRESULT
0x180056e24  mov     [rbp+var_40], eax
0x180056e27  mov     eax, 53Ah
0x180056e2c  jmp     short loc_180056EAD
0x180056e2e  mov     [rbp+var_40], r14d
0x180056e32  mov     eax, 53Ah
0x180056e37  mov     [rbp+var_3C], ax
0x180056e3b  mov     rcx, [rbp+StringSid]
0x180056e3f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180056e43  inc     rax
0x180056e46  cmp     [rcx+rax*2], r14w
0x180056e4b  jnz     short loc_180056E43
0x180056e4d  inc     eax
0x180056e4f  mov     esi, eax
0x180056e51  lea     rcx, [rax+rax]; cb
0x180056e55  call    cs:__imp_CoTaskMemAlloc
0x180056e5c  nop     dword ptr [rax+rax+00h]
0x180056e61  mov     rbx, rax
0x180056e64  test    rax, rax
0x180056e67  mov     eax, 53Eh
0x180056e6c  jnz     short loc_180056E77
0x180056e6e  mov     [rbp+var_40], 8007000Eh
0x180056e75  jmp     short loc_180056EAD
0x180056e77  mov     [rbp+var_40], r14d
0x180056e7b  mov     [rbp+var_3C], ax
0x180056e7f  mov     r8, [rbp+StringSid]; unsigned __int16 *
0x180056e83  mov     rdx, rsi; unsigned __int64
0x180056e86  mov     rcx, rbx; unsigned __int16 *
0x180056e89  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180056e8e  mov     [rbp+var_40], eax
0x180056e91  test    eax, eax
0x180056e93  mov     eax, 53Fh
0x180056e98  js      short loc_180056EAD
0x180056e9a  mov     [rbp+var_3C], ax
0x180056e9e  mov     [rdi], rbx
0x180056ea1  mov     rbx, r14
0x180056ea4  jmp     short loc_180056EB1
0x180056ea6  mov     [rbp+var_40], 80070057h
0x180056ead  mov     [rbp+var_3A], ax
0x180056eb1  mov     rcx, rbx; pv
0x180056eb4  call    cs:__imp_CoTaskMemFree
0x180056ebb  nop     dword ptr [rax+rax+00h]
0x180056ec0  mov     rcx, [rbp+StringSid]; hMem
0x180056ec4  test    rcx, rcx
0x180056ec7  jz      short loc_180056ED9
0x180056ec9  call    cs:__imp_LocalFree
0x180056ed0  nop     dword ptr [rax+rax+00h]
0x180056ed5  mov     [rbp+StringSid], r14
0x180056ed9  mov     ebx, [rbp+var_40]
0x180056edc  lea     rcx, [rbp+var_40]; this
0x180056ee0  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180056ee5  mov     eax, ebx
0x180056ee7  lea     r11, [rsp+60h+var_s0]
0x180056eec  mov     rbx, [r11+20h]
0x180056ef0  mov     rsi, [r11+30h]
0x180056ef4  mov     rsp, r11
0x180056ef7  pop     r14
0x180056ef9  pop     rdi
0x180056efa  pop     rbp
0x180056efb  retn
```
