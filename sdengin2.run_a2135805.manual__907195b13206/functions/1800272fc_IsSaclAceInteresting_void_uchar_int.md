# IsSaclAceInteresting(void *,uchar,int *)

- ea: `0x1800272fc`
- end: `0x1800273f6`
- name: `?IsSaclAceInteresting@@YAJPEAXEPEAH@Z`
- size: `250`
- prototype: `__int64 __fastcall(void *, unsigned __int8, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800252f0`

## callees

- `0x1800272fc`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800273bb`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800273bb`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800273a7`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800273a7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180027372`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180027372`

## string_xrefs

- `0x180027320`: `IsSaclAceInteresting`

## pseudocode

```c
__int64 __fastcall IsSaclAceInteresting(char *a1, char a2, int *a3)
{
  __int16 v6; // ax
  char *v7; // rdi
  __int64 v8; // rcx
  PUCHAR SidSubAuthorityCount; // rax
  unsigned int v10; // ebx
  int LastFailureAsHRESULT; // [rsp+20h] [rbp-48h] BYREF
  __int16 v13; // [rsp+24h] [rbp-44h]
  __int16 v14; // [rsp+26h] [rbp-42h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "IsSaclAceInteresting", 0x1FFu, 1u);
  v6 = 517;
  if ( !a1 )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_3:
    v14 = v6;
    goto LABEL_11;
  }
  LastFailureAsHRESULT = 0;
  v13 = 517;
  if ( a3 )
    *a3 = 0;
  if ( a2 == 17 )
  {
    v7 = a1 + 8;
    if ( !IsValidSid(v7) )
    {
      LastFailureAsHRESULT = GetLastFailureAsHRESULT(v8);
      v6 = 523;
      goto LABEL_3;
    }
    LastFailureAsHRESULT = 0;
    v13 = 523;
    SidSubAuthorityCount = GetSidSubAuthorityCount(v7);
    if ( *GetSidSubAuthority(v7, (unsigned int)*SidSubAuthorityCount - 1) < 0x3000 )
      *a3 = 1;
  }
LABEL_11:
  v10 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v10;
}

```

## disassembly

```asm
0x1800272fc  mov     [rsp+arg_0], rbx
0x180027301  mov     [rsp+arg_8], rsi
0x180027306  push    rdi
0x180027307  sub     rsp, 60h
0x18002730b  mov     rbx, r8
0x18002730e  mov     sil, dl
0x180027311  mov     rdi, rcx
0x180027314  mov     r9d, 1; unsigned __int16
0x18002731a  mov     r8d, 1FFh; unsigned __int16
0x180027320  lea     rdx, aIssaclaceinter; "IsSaclAceInteresting"
0x180027327  lea     rcx, [rsp+68h+var_48]; this
0x18002732c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180027331  mov     eax, 205h
0x180027336  test    rdi, rdi
0x180027339  jnz     short loc_18002734D
0x18002733b  mov     [rsp+68h+var_48], 80070057h
0x180027343  mov     [rsp+68h+var_42], ax
0x180027348  jmp     loc_1800273D5
0x18002734d  mov     [rsp+68h+var_48], 0
0x180027355  mov     [rsp+68h+var_44], ax
0x18002735a  test    rbx, rbx
0x18002735d  jz      short loc_180027365
0x18002735f  mov     dword ptr [rbx], 0
0x180027365  cmp     sil, 11h
0x180027369  jnz     short loc_1800273D5
0x18002736b  add     rdi, 8
0x18002736f  mov     rcx, rdi; pSid
0x180027372  call    cs:__imp_IsValidSid
0x180027379  nop     dword ptr [rax+rax+00h]
0x18002737e  test    eax, eax
0x180027380  jnz     short loc_180027392
0x180027382  call    GetLastFailureAsHRESULT
0x180027387  mov     [rsp+68h+var_48], eax
0x18002738b  mov     eax, 20Bh
0x180027390  jmp     short loc_180027343
0x180027392  mov     [rsp+68h+var_48], 0
0x18002739a  mov     eax, 20Bh
0x18002739f  mov     [rsp+68h+var_44], ax
0x1800273a4  mov     rcx, rdi; pSid
0x1800273a7  call    cs:__imp_GetSidSubAuthorityCount
0x1800273ae  nop     dword ptr [rax+rax+00h]
0x1800273b3  movzx   edx, byte ptr [rax]
0x1800273b6  dec     edx; nSubAuthority
0x1800273b8  mov     rcx, rdi; pSid
0x1800273bb  call    cs:__imp_GetSidSubAuthority
0x1800273c2  nop     dword ptr [rax+rax+00h]
0x1800273c7  cmp     dword ptr [rax], 3000h
0x1800273cd  jnb     short loc_1800273D5
0x1800273cf  mov     dword ptr [rbx], 1
0x1800273d5  mov     ebx, [rsp+68h+var_48]
0x1800273d9  lea     rcx, [rsp+68h+var_48]; this
0x1800273de  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800273e3  mov     eax, ebx
0x1800273e5  mov     rbx, [rsp+68h+arg_0]
0x1800273ea  mov     rsi, [rsp+68h+arg_8]
0x1800273ef  add     rsp, 60h
0x1800273f3  pop     rdi
0x1800273f4  retn
```
