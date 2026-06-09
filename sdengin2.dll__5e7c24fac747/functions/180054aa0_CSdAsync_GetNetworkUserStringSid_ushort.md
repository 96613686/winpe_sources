# CSdAsync::GetNetworkUserStringSid(ushort * *)

- ea: `0x180054aa0`
- end: `0x180054c1e`
- name: `?GetNetworkUserStringSid@CSdAsync@@UEAAJPEAPEAG@Z`
- size: `382`
- prototype: `__int64 __fastcall(CSdAsync *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180009ac8`
- `0x180054aa0`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180054bf1`
- `KERNEL32!LocalFree` at `0x180054bf1`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180054b1b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180054b1b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180054b49`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180054b49`
- `ole32!CoTaskMemFree` at `0x180054be2`
- `ole32!CoTaskMemFree` at `0x180054be2`
- `ole32!CoTaskMemAlloc` at `0x180054b89`
- `ole32!CoTaskMemAlloc` at `0x180054b89`

## string_xrefs

- `0x180054ac7`: `CSdAsync::GetNetworkUserStringSid`

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
    1322,
    1);
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
0x180054aa0  mov     [rsp-18h+arg_0], rbx
0x180054aa5  mov     [rsp-18h+arg_10], rsi
0x180054aaa  push    rbp
0x180054aab  push    rdi
0x180054aac  push    r14
0x180054aae  mov     rbp, rsp
0x180054ab1  sub     rsp, 60h
0x180054ab5  mov     rdi, rdx
0x180054ab8  mov     rsi, rcx
0x180054abb  mov     r9d, 1; unsigned __int16
0x180054ac1  mov     r8d, 52Ah; unsigned __int16
0x180054ac7  lea     rdx, aCsdasyncGetnet; "CSdAsync::GetNetworkUserStringSid"
0x180054ace  lea     rcx, [rbp+var_40]; this
0x180054ad2  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180054ad7  xor     r14d, r14d
0x180054ada  mov     [rbp+StringSid], r14
0x180054ade  mov     ebx, r14d
0x180054ae1  mov     eax, 532h
0x180054ae6  test    rdi, rdi
0x180054ae9  jz      loc_180054BD4
0x180054aef  mov     [rdi], r14
0x180054af2  mov     [rbp+var_40], r14d
0x180054af6  mov     [rbp+var_3C], ax
0x180054afa  mov     rcx, [rsi+118h]; pSid
0x180054b01  test    rcx, rcx
0x180054b04  jnz     short loc_180054B1B
0x180054b06  mov     [rbp+var_40], 1
0x180054b0d  mov     eax, 536h
0x180054b12  mov     [rbp+var_3C], ax
0x180054b16  jmp     loc_180054BDF
0x180054b1b  call    cs:__imp_IsValidSid
0x180054b21  test    eax, eax
0x180054b23  mov     eax, 539h
0x180054b28  jnz     short loc_180054B36
0x180054b2a  mov     [rbp+var_40], 80004005h
0x180054b31  jmp     loc_180054BDB
0x180054b36  mov     [rbp+var_40], r14d
0x180054b3a  mov     [rbp+var_3C], ax
0x180054b3e  lea     rdx, [rbp+StringSid]; StringSid
0x180054b42  mov     rcx, [rsi+118h]; Sid
0x180054b49  call    cs:__imp_ConvertSidToStringSidW
0x180054b4f  test    eax, eax
0x180054b51  jnz     short loc_180054B62
0x180054b53  call    GetLastFailureAsHRESULT
0x180054b58  mov     [rbp+var_40], eax
0x180054b5b  mov     eax, 53Ah
0x180054b60  jmp     short loc_180054BDB
0x180054b62  mov     [rbp+var_40], r14d
0x180054b66  mov     eax, 53Ah
0x180054b6b  mov     [rbp+var_3C], ax
0x180054b6f  mov     rcx, [rbp+StringSid]
0x180054b73  or      rax, 0FFFFFFFFFFFFFFFFh
0x180054b77  inc     rax
0x180054b7a  cmp     [rcx+rax*2], r14w
0x180054b7f  jnz     short loc_180054B77
0x180054b81  inc     eax
0x180054b83  mov     esi, eax
0x180054b85  lea     rcx, [rax+rax]; cb
0x180054b89  call    cs:__imp_CoTaskMemAlloc
0x180054b8f  mov     rbx, rax
0x180054b92  test    rax, rax
0x180054b95  mov     eax, 53Eh
0x180054b9a  jnz     short loc_180054BA5
0x180054b9c  mov     [rbp+var_40], 8007000Eh
0x180054ba3  jmp     short loc_180054BDB
0x180054ba5  mov     [rbp+var_40], r14d
0x180054ba9  mov     [rbp+var_3C], ax
0x180054bad  mov     r8, [rbp+StringSid]; unsigned __int16 *
0x180054bb1  mov     rdx, rsi; unsigned __int64
0x180054bb4  mov     rcx, rbx; unsigned __int16 *
0x180054bb7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180054bbc  mov     [rbp+var_40], eax
0x180054bbf  test    eax, eax
0x180054bc1  mov     eax, 53Fh
0x180054bc6  js      short loc_180054BDB
0x180054bc8  mov     [rbp+var_3C], ax
0x180054bcc  mov     [rdi], rbx
0x180054bcf  mov     rbx, r14
0x180054bd2  jmp     short loc_180054BDF
0x180054bd4  mov     [rbp+var_40], 80070057h
0x180054bdb  mov     [rbp+var_3A], ax
0x180054bdf  mov     rcx, rbx; pv
0x180054be2  call    cs:__imp_CoTaskMemFree
0x180054be8  mov     rcx, [rbp+StringSid]; hMem
0x180054bec  test    rcx, rcx
0x180054bef  jz      short loc_180054BFB
0x180054bf1  call    cs:__imp_LocalFree
0x180054bf7  mov     [rbp+StringSid], r14
0x180054bfb  mov     ebx, [rbp+var_40]
0x180054bfe  lea     rcx, [rbp+var_40]; this
0x180054c02  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180054c07  mov     eax, ebx
0x180054c09  lea     r11, [rsp+60h+var_s0]
0x180054c0e  mov     rbx, [r11+20h]
0x180054c12  mov     rsi, [r11+30h]
0x180054c16  mov     rsp, r11
0x180054c19  pop     r14
0x180054c1b  pop     rdi
0x180054c1c  pop     rbp
0x180054c1d  retn
```
