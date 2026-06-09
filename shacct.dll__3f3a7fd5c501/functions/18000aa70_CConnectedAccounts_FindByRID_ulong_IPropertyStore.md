# CConnectedAccounts::FindByRID(ulong,IPropertyStore * *)

- ea: `0x18000aa70`
- end: `0x18000ad0b`
- name: `?FindByRID@CConnectedAccounts@@UEAAJKPEAPEAUIPropertyStore@@@Z`
- size: `667`
- prototype: `__int64 __fastcall(CConnectedAccounts *__hidden this, unsigned int, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000aa70`
- `0x18000ad20`
- `0x18000c240`
- `0x180017010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ac9a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000ac9a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000ab93`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18000ab93`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000aba1`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18000aba1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aca4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000aca4`
- `PROPSYS!PropVariantToStringAlloc` at `0x18000ab4d`
- `PROPSYS!PropVariantToStringAlloc` at `0x18000ab4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000acae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000acae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ab59`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000acb6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000ab59`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000acb6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000ab77`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000ab77`

## pseudocode

```c
__int64 __fastcall CConnectedAccounts::FindByRID(CConnectedAccounts *this, int a2, struct IPropertyStore **a3)
{
  __int64 result; // rax
  char v6; // r14
  int v7; // esi
  unsigned int v8; // r15d
  int *v9; // rax
  int v10; // ecx
  __int64 v11; // rax
  struct IPropertyStore *v12; // rdi
  HRESULT v13; // ebx
  PSID v14; // rbx
  DWORD v15; // eax
  PUCHAR SidSubAuthorityCount; // rax
  PWSTR v17; // rcx
  __int64 v18; // rax
  int v20; // eax
  PWSTR ppszOut; // [rsp+30h] [rbp-39h] BYREF
  int v22; // [rsp+38h] [rbp-31h]
  unsigned int v23; // [rsp+3Ch] [rbp-2Dh]
  PSID Sid; // [rsp+40h] [rbp-29h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-21h] BYREF
  PROPVARIANT propvar[2]; // [rsp+58h] [rbp-11h] BYREF
  char *v27; // [rsp+68h] [rbp-1h]
  int v28; // [rsp+70h] [rbp+7h]
  int v29; // [rsp+74h] [rbp+Bh]
  PWSTR v30; // [rsp+78h] [rbp+Fh]
  int v31; // [rsp+80h] [rbp+17h]
  int v32; // [rsp+84h] [rbp+1Bh]

  v22 = a2;
  *a3 = 0;
  result = CConnectedAccounts::_Init(this);
  if ( (int)result >= 0 )
  {
    v6 = 0;
    v7 = 0;
    v8 = -2147024809;
    do
    {
      v9 = (int *)*((_QWORD *)this + 2);
      if ( v9 )
        v10 = *v9;
      else
        v10 = 0;
      if ( v7 >= v10 )
        break;
      v11 = *((_QWORD *)v9 + 1);
      *(_OWORD *)propvar = 0;
      v12 = *(struct IPropertyStore **)(v11 + 8LL * v7);
      v27 = 0;
      ppszOut = 0;
      if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v12->lpVtbl->GetValue)(
             v12,
             &PKEY_Identity_PrimarySid,
             propvar) >= 0 )
      {
        if ( LOWORD(propvar[0]) )
        {
          v13 = PropVariantToStringAlloc(propvar, &ppszOut);
          PropVariantClear(propvar);
          if ( v13 >= 0 )
          {
            Sid = 0;
            if ( ConvertStringSidToSidW(ppszOut, &Sid) )
            {
              v14 = Sid;
              v15 = 0;
              if ( Sid )
              {
                SidSubAuthorityCount = GetSidSubAuthorityCount(Sid);
                v15 = *GetSidSubAuthority(v14, (unsigned int)*SidSubAuthorityCount - 1);
              }
              if ( v15 == v22 )
              {
                *a3 = v12;
                ((void (__fastcall *)(struct IPropertyStore *))v12->lpVtbl->AddRef)(v12);
                v8 = 0;
                v6 = 1;
                if ( (unsigned int)dword_18001F000 > 4 )
                {
                  v17 = ppszOut;
                  if ( ppszOut )
                  {
                    v18 = -1;
                    while ( ppszOut[++v18] != 0 )
                      ;
                    v20 = 2 * v18 + 2;
                  }
                  else
                  {
                    v17 = (PWSTR)&qword_18001B188;
                    v20 = 2;
                  }
                  v31 = v20;
                  *(_DWORD *)&EventDescriptor.Level = 4;
                  propvar[0] = off_18001F008;
                  v30 = v17;
                  v32 = 0;
                  *(_DWORD *)&EventDescriptor.Id = 184549376;
                  EventDescriptor.Keyword = 0;
                  propvar[1] = (PROPVARIANT)(*(unsigned __int16 *)off_18001F008 | 0x200000000LL);
                  v27 = byte_18001B633;
                  v28 = 51;
                  v29 = 1;
                  v23 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                  EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, (PEVENT_DATA_DESCRIPTOR)propvar);
                }
              }
              LocalFree(Sid);
            }
            CoTaskMemFree(ppszOut);
          }
        }
        else
        {
          PropVariantClear(propvar);
        }
      }
      ++v7;
    }
    while ( !v6 );
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18000aa70  push    rbp
0x18000aa72  push    r12
0x18000aa74  push    r13
0x18000aa76  lea     rbp, [rsp-47h]
0x18000aa7b  sub     rsp, 0B0h
0x18000aa82  mov     rax, cs:__security_cookie
0x18000aa89  xor     rax, rsp
0x18000aa8c  mov     [rbp+57h+var_38], rax
0x18000aa90  mov     r12, r8
0x18000aa93  mov     [rbp+57h+var_88], edx
0x18000aa96  mov     r13, rcx
0x18000aa99  mov     qword ptr [r8], 0
0x18000aaa0  call    ?_Init@CConnectedAccounts@@AEAAJXZ; CConnectedAccounts::_Init(void)
0x18000aaa5  test    eax, eax
0x18000aaa7  js      loc_18000ACF2
0x18000aaad  mov     [rsp+0C0h+var_18], rsi
0x18000aab5  mov     [rsp+0C0h+var_28], r14
0x18000aabd  xor     r14b, r14b
0x18000aac0  mov     [rsp+0C0h+var_30], r15
0x18000aac8  xor     esi, esi
0x18000aaca  mov     [rsp+0C0h+arg_8], rbx
0x18000aad2  mov     r15d, 80070057h
0x18000aad8  mov     [rsp+0C0h+var_20], rdi
0x18000aae0  mov     rax, [r13+10h]
0x18000aae4  test    rax, rax
0x18000aae7  jz      short loc_18000AAED
0x18000aae9  mov     ecx, [rax]
0x18000aaeb  jmp     short loc_18000AAEF
0x18000aaed  xor     ecx, ecx
0x18000aaef  cmp     esi, ecx
0x18000aaf1  jge     loc_18000ACC7
0x18000aaf7  mov     rax, [rax+8]
0x18000aafb  lea     r8, [rbp+57h+propvar]
0x18000aaff  movsxd  rcx, esi
0x18000ab02  lea     rdx, PKEY_Identity_PrimarySid
0x18000ab09  xorps   xmm0, xmm0
0x18000ab0c  movups  xmmword ptr [rbp+57h+propvar], xmm0
0x18000ab10  mov     rdi, [rax+rcx*8]
0x18000ab14  xor     eax, eax
0x18000ab16  mov     [rbp+57h+var_58], rax
0x18000ab1a  mov     rcx, rdi
0x18000ab1d  mov     [rbp+57h+ppszOut], 0
0x18000ab25  mov     rax, [rdi]
0x18000ab28  mov     rax, [rax+28h]
0x18000ab2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab31  test    eax, eax
0x18000ab33  js      loc_18000ACBC
0x18000ab39  xor     eax, eax
0x18000ab3b  lea     rcx, [rbp+57h+propvar]; pvar
0x18000ab3f  cmp     ax, word ptr [rbp+57h+propvar]
0x18000ab43  jz      loc_18000ACB6
0x18000ab49  lea     rdx, [rbp+57h+ppszOut]; ppszOut
0x18000ab4d  call    cs:__imp_PropVariantToStringAlloc
0x18000ab53  lea     rcx, [rbp+57h+propvar]; pvar
0x18000ab57  mov     ebx, eax
0x18000ab59  call    cs:__imp_PropVariantClear
0x18000ab5f  test    ebx, ebx
0x18000ab61  js      loc_18000ACBC
0x18000ab67  mov     rcx, [rbp+57h+ppszOut]; StringSid
0x18000ab6b  lea     rdx, [rbp+57h+Sid]; Sid
0x18000ab6f  mov     [rbp+57h+Sid], 0
0x18000ab77  call    cs:__imp_ConvertStringSidToSidW
0x18000ab7d  test    eax, eax
0x18000ab7f  jz      loc_18000ACAA
0x18000ab85  mov     rbx, [rbp+57h+Sid]
0x18000ab89  xor     eax, eax
0x18000ab8b  test    rbx, rbx
0x18000ab8e  jz      short loc_18000ABA9
0x18000ab90  mov     rcx, rbx; pSid
0x18000ab93  call    cs:__imp_GetSidSubAuthorityCount
0x18000ab99  mov     rcx, rbx; pSid
0x18000ab9c  movzx   edx, byte ptr [rax]
0x18000ab9f  dec     edx; nSubAuthority
0x18000aba1  call    cs:__imp_GetSidSubAuthority
0x18000aba7  mov     eax, [rax]
0x18000aba9  cmp     eax, [rbp+57h+var_88]
0x18000abac  jnz     loc_18000ACA0
0x18000abb2  mov     [r12], rdi
0x18000abb6  mov     rcx, rdi
0x18000abb9  mov     rax, [rdi]
0x18000abbc  mov     rax, [rax+8]
0x18000abc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abc5  mov     eax, cs:dword_18001F000
0x18000abcb  xor     r15d, r15d
0x18000abce  mov     r14b, 1
0x18000abd1  cmp     eax, 4
0x18000abd4  jbe     loc_18000ACA0
0x18000abda  mov     rcx, [rbp+57h+ppszOut]
0x18000abde  test    rcx, rcx
0x18000abe1  jz      short loc_18000AC05
0x18000abe3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000abea  nop     word ptr [rax+rax+00h]
0x18000abf0  cmp     [rcx+rax*2+2], r15w
0x18000abf6  lea     rax, [rax+1]
0x18000abfa  jnz     short loc_18000ABF0
0x18000abfc  lea     eax, ds:2[rax*2]
0x18000ac03  jmp     short loc_18000AC11
0x18000ac05  lea     rcx, qword_18001B188
0x18000ac0c  mov     eax, 2
0x18000ac11  mov     [rbp+57h+var_40], eax
0x18000ac14  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18000ac18  movzx   eax, cs:word_18001B629
0x18000ac1f  xor     r9d, r9d; RelatedActivityId
0x18000ac22  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18000ac25  xor     r8d, r8d; ActivityId
0x18000ac28  mov     rax, cs:off_18001F008
0x18000ac2f  mov     [rbp+57h+propvar], rax
0x18000ac33  mov     [rbp+57h+var_48], rcx
0x18000ac37  lea     rcx, _TraceLoggingMetadata
0x18000ac3e  mov     [rbp+57h+var_3C], r15d
0x18000ac42  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18000ac49  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x18000ac4d  movzx   eax, word ptr [rax]
0x18000ac50  mov     dword ptr [rbp+57h+propvar+8], eax
0x18000ac53  lea     rax, byte_18001B633
0x18000ac5a  mov     [rbp+57h+var_58], rax
0x18000ac5e  lea     rax, _TraceLoggingMetadataEnd
0x18000ac65  sub     eax, ecx
0x18000ac67  mov     dword ptr [rbp+57h+propvar+0Ch], 2
0x18000ac6e  mov     [rbp+57h+var_50], 33h ; '3'
0x18000ac75  mov     [rbp+57h+var_4C], 1
0x18000ac7c  mov     [rbp+57h+var_84], eax
0x18000ac7f  mov     eax, [rbp+57h+var_84]
0x18000ac82  mov     rcx, cs:RegHandle; RegHandle
0x18000ac89  lea     rax, [rbp+57h+propvar]
0x18000ac8d  mov     [rsp+0C0h+UserData], rax; UserData
0x18000ac92  mov     [rsp+0C0h+UserDataCount], 3; UserDataCount
0x18000ac9a  call    cs:__imp_EventWriteTransfer
0x18000aca0  mov     rcx, [rbp+57h+Sid]; hMem
0x18000aca4  call    cs:__imp_LocalFree
0x18000acaa  mov     rcx, [rbp+57h+ppszOut]; pv
0x18000acae  call    cs:__imp_CoTaskMemFree
0x18000acb4  jmp     short loc_18000ACBC
0x18000acb6  call    cs:__imp_PropVariantClear
0x18000acbc  inc     esi
0x18000acbe  test    r14b, r14b
0x18000acc1  jz      loc_18000AAE0
0x18000acc7  mov     rdi, [rsp+0C0h+var_20]
0x18000accf  mov     eax, r15d
0x18000acd2  mov     r15, [rsp+0C0h+var_30]
0x18000acda  mov     rbx, [rsp+0C0h+arg_8]
0x18000ace2  mov     rsi, [rsp+0C0h+var_18]
0x18000acea  mov     r14, [rsp+0C0h+var_28]
0x18000acf2  mov     rcx, [rbp+57h+var_38]
0x18000acf6  xor     rcx, rsp; StackCookie
0x18000acf9  call    __security_check_cookie
0x18000acfe  add     rsp, 0B0h
0x18000ad05  pop     r13
0x18000ad07  pop     r12
0x18000ad09  pop     rbp
0x18000ad0a  retn
```
