# NdrpLogIIDMisMatchEvent(_GUID *,_GUID *)

- ea: `0x1800c4690`
- end: `0x1800c47bd`
- name: `?NdrpLogIIDMisMatchEvent@@YAXPEFAU_GUID@@PEAU1@@Z`
- size: `301`
- prototype: `void(struct _GUID *, struct _GUID *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18002d310`
- `0x180086460`
- `0x1800c4690`
- `0x1800c4a18`
- `0x1800ceda0`

## import_xrefs

- `ntdll!RtlIntegerToUnicodeString` at `0x1800c4740`
- `ntdll!RtlIntegerToUnicodeString` at `0x1800c4740`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800c4755`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x1800c4755`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c472c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800c472c`

## pseudocode

```c
void __fastcall NdrpLogIIDMisMatchEvent(struct _GUID *a1, struct _GUID *a2)
{
  UUID v3; // xmm1
  RPC_WSTR v4; // rdi
  RPC_WSTR v5; // rbx
  ULONG CurrentProcessId; // eax
  unsigned int CommandLineW; // eax
  int v8; // edx
  int v9; // ecx
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-50h] BYREF
  RPC_WSTR v11; // [rsp+38h] [rbp-48h] BYREF
  struct _UNICODE_STRING String; // [rsp+40h] [rbp-40h] BYREF
  UUID Uuid; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v14[24]; // [rsp+60h] [rbp-20h] BYREF

  if ( !byte_1800FF466 )
  {
    v3 = *a1;
    StringUuid = 0;
    v11 = 0;
    Uuid = v3;
    String = 0;
    if ( !UuidToStringW(&Uuid, &StringUuid) )
    {
      v4 = StringUuid;
      if ( StringUuid )
      {
        if ( UuidToStringW(a2, &v11) || (v5 = v11) == 0 )
        {
          RpcStringFreeW(&StringUuid);
        }
        else
        {
          *(_DWORD *)&String.Length = 1441792;
          String.Buffer = (PWSTR)v14;
          CurrentProcessId = GetCurrentProcessId();
          RtlIntegerToUnicodeString(CurrentProcessId, 0, &String);
          if ( (Microsoft_Windows_RPC_EventsEnableBits & 1) != 0 )
          {
            CommandLineW = (unsigned int)GetCommandLineW();
            McTemplateU0zzzz_EtwEventWriteTransfer(v9, v8, CommandLineW, (unsigned int)v14, (__int64)v4, (__int64)v5);
          }
          RpcStringFreeW(&StringUuid);
          RpcStringFreeW(&v11);
          byte_1800FF466 = 1;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800c4690  mov     [rsp-8+arg_10], rbx
0x1800c4695  mov     [rsp-8+arg_18], rdi
0x1800c469a  push    rbp
0x1800c469b  mov     rbp, rsp
0x1800c469e  sub     rsp, 80h
0x1800c46a5  mov     rax, cs:__security_cookie
0x1800c46ac  xor     rax, rsp
0x1800c46af  mov     [rbp+var_8], rax
0x1800c46b3  cmp     cs:byte_1800FF466, 0
0x1800c46ba  mov     rbx, rdx
0x1800c46bd  jnz     loc_1800C479B
0x1800c46c3  movups  xmm1, xmmword ptr [rcx]
0x1800c46c6  mov     [rbp+StringUuid], 0
0x1800c46ce  lea     rdx, [rbp+StringUuid]; StringUuid
0x1800c46d2  xorps   xmm0, xmm0
0x1800c46d5  mov     [rbp+var_48], 0
0x1800c46dd  lea     rcx, [rbp+Uuid]; Uuid
0x1800c46e1  movdqu  xmmword ptr [rbp+Uuid.Data1], xmm1
0x1800c46e6  movups  xmmword ptr [rbp+String.Length], xmm0
0x1800c46ea  call    UuidToStringW
0x1800c46ef  test    eax, eax
0x1800c46f1  jnz     loc_1800C479B
0x1800c46f7  mov     rdi, [rbp+StringUuid]
0x1800c46fb  test    rdi, rdi
0x1800c46fe  jz      loc_1800C479B
0x1800c4704  lea     rdx, [rbp+var_48]; StringUuid
0x1800c4708  mov     rcx, rbx; Uuid
0x1800c470b  call    UuidToStringW
0x1800c4710  test    eax, eax
0x1800c4712  jnz     short loc_1800C4792
0x1800c4714  mov     rbx, [rbp+var_48]
0x1800c4718  test    rbx, rbx
0x1800c471b  jz      short loc_1800C4792
0x1800c471d  lea     rax, [rbp+var_20]
0x1800c4721  mov     dword ptr [rbp+String.Length], 160000h
0x1800c4728  mov     [rbp+String.Buffer], rax
0x1800c472c  call    cs:__imp_GetCurrentProcessId
0x1800c4733  nop     dword ptr [rax+rax+00h]
0x1800c4738  lea     r8, [rbp+String]; String
0x1800c473c  xor     edx, edx; Base
0x1800c473e  mov     ecx, eax; Value
0x1800c4740  call    cs:__imp_RtlIntegerToUnicodeString
0x1800c4747  nop     dword ptr [rax+rax+00h]
0x1800c474c  test    cs:Microsoft_Windows_RPC_EventsEnableBits, 1
0x1800c4753  jz      short loc_1800C4777
0x1800c4755  call    cs:__imp_GetCommandLineW
0x1800c475c  nop     dword ptr [rax+rax+00h]
0x1800c4761  mov     [rsp+80h+var_58], rbx
0x1800c4766  lea     r9, [rbp+var_20]
0x1800c476a  mov     r8, rax
0x1800c476d  mov     [rsp+80h+var_60], rdi
0x1800c4772  call    McTemplateU0zzzz_EtwEventWriteTransfer
0x1800c4777  lea     rcx, [rbp+StringUuid]; String
0x1800c477b  call    RpcStringFreeW
0x1800c4780  lea     rcx, [rbp+var_48]; String
0x1800c4784  call    RpcStringFreeW
0x1800c4789  mov     cs:byte_1800FF466, 1
0x1800c4790  jmp     short loc_1800C479B
0x1800c4792  lea     rcx, [rbp+StringUuid]; String
0x1800c4796  call    RpcStringFreeW
0x1800c479b  mov     rcx, [rbp+var_8]
0x1800c479f  xor     rcx, rsp; StackCookie
0x1800c47a2  call    __security_check_cookie
0x1800c47a7  lea     r11, [rsp+80h+var_s0]
0x1800c47af  mov     rbx, [r11+20h]
0x1800c47b3  mov     rdi, [r11+28h]
0x1800c47b7  mov     rsp, r11
0x1800c47ba  pop     rbp
0x1800c47bb  retn
```
