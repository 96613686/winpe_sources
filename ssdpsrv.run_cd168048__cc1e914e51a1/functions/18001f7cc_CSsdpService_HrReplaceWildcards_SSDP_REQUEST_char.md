# CSsdpService::HrReplaceWildcards(_SSDP_REQUEST *,char *)

- ea: `0x18001f7cc`
- end: `0x18001f8be`
- name: `?HrReplaceWildcards@CSsdpService@@IEAAJPEAU_SSDP_REQUEST@@PEAD@Z`
- size: `242`
- prototype: `int(CSsdpService *__hidden this, struct _SSDP_REQUEST *, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800040e0`

## callees

- `0x180011c44`
- `0x18001f7cc`
- `0x1800287d0`
- `0x180032124`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18001f7fa`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18001f7fa`

## pseudocode

```c
__int64 __fastcall CSsdpService::HrReplaceWildcards(CSsdpService *this, const struct _GUID *a2, char *a3)
{
  int PhysicalAddress; // ebx
  char *v5; // rdi
  unsigned int i; // edx
  __int64 v7; // rcx
  unsigned int v9; // [rsp+50h] [rbp+7h] BYREF
  unsigned __int8 v10[8]; // [rsp+58h] [rbp+Fh] BYREF
  char v11[24]; // [rsp+60h] [rbp+17h] BYREF

  PhysicalAddress = 0;
  v5 = strstr(a3, "%SSDPMACADDRESS_%");
  if ( v5 )
  {
    v9 = 8;
    PhysicalAddress = CInterfaceHelper::HrGetPhysicalAddress(
                        (CInterfaceHelper *)&CInterfaceHelper::s_instance,
                        a2 + 2,
                        v10,
                        &v9);
    if ( PhysicalAddress >= 0 )
    {
      if ( v9 < 6 )
      {
        return 1168;
      }
      else
      {
        PhysicalAddress = StringCchPrintfA(
                            v11,
                            0x12u,
                            "%02x:%02x:%02x:%02x:%02x:%02x",
                            v10[0],
                            v10[1],
                            v10[2],
                            v10[3],
                            v10[4],
                            v10[5]);
        if ( PhysicalAddress >= 0 )
        {
          for ( i = 0; i < 0x11; ++i )
          {
            v7 = (int)i;
            v5[v7] = v11[v7];
          }
        }
      }
    }
  }
  return (unsigned int)PhysicalAddress;
}

```

## disassembly

```asm
0x18001f7cc  push    rbp
0x18001f7ce  push    rbx
0x18001f7cf  push    rsi
0x18001f7d0  push    rdi
0x18001f7d1  lea     rbp, [rsp-3Fh]
0x18001f7d6  sub     rsp, 88h
0x18001f7dd  mov     rax, cs:__security_cookie
0x18001f7e4  xor     rax, rsp
0x18001f7e7  mov     [rbp+57h+var_28], rax
0x18001f7eb  mov     rsi, rdx
0x18001f7ee  mov     rcx, r8; Str
0x18001f7f1  lea     rdx, aSsdpmacaddress; "%SSDPMACADDRESS_%"
0x18001f7f8  xor     ebx, ebx
0x18001f7fa  call    cs:__imp_strstr
0x18001f801  nop     dword ptr [rax+rax+00h]
0x18001f806  mov     rdi, rax
0x18001f809  test    rax, rax
0x18001f80c  jz      loc_18001F8A3
0x18001f812  lea     rdx, [rsi+20h]; struct _GUID *
0x18001f816  mov     [rbp+57h+var_50], 8
0x18001f81d  lea     r9, [rbp+57h+var_50]; unsigned int *
0x18001f821  lea     r8, [rbp+57h+var_48]; unsigned __int8 *
0x18001f825  lea     rcx, ?s_instance@CInterfaceHelper@@0V1@A; this
0x18001f82c  call    ?HrGetPhysicalAddress@CInterfaceHelper@@QEAAJAEBU_GUID@@PEAEPEAK@Z; CInterfaceHelper::HrGetPhysicalAddress(_GUID const &,uchar *,ulong *)
0x18001f831  mov     ebx, eax
0x18001f833  test    eax, eax
0x18001f835  js      short loc_18001F8A3
0x18001f837  cmp     [rbp+57h+var_50], 6
0x18001f83b  jb      short loc_18001F89E
0x18001f83d  movzx   eax, [rbp+57h+var_43]
0x18001f841  movzx   ecx, [rbp+57h+var_44]
0x18001f845  movzx   edx, [rbp+57h+var_45]
0x18001f849  movzx   r8d, [rbp+57h+var_46]
0x18001f84e  movzx   r10d, [rbp+57h+var_47]
0x18001f853  movzx   r9d, [rbp+57h+var_48]
0x18001f858  mov     [rsp+0A0h+var_60], eax
0x18001f85c  mov     [rsp+0A0h+var_68], ecx
0x18001f860  lea     rcx, [rbp+57h+var_40]; char *
0x18001f864  mov     [rsp+0A0h+var_70], edx
0x18001f868  mov     edx, 12h; unsigned __int64
0x18001f86d  mov     [rsp+0A0h+var_78], r8d
0x18001f872  lea     r8, a02x02x02x02x02; "%02x:%02x:%02x:%02x:%02x:%02x"
0x18001f879  mov     [rsp+0A0h+var_80], r10d
0x18001f87e  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001f883  mov     ebx, eax
0x18001f885  test    eax, eax
0x18001f887  js      short loc_18001F8A3
0x18001f889  xor     edx, edx
0x18001f88b  movsxd  rcx, edx
0x18001f88e  inc     edx
0x18001f890  mov     al, [rbp+rcx+57h+var_40]
0x18001f894  mov     [rcx+rdi], al
0x18001f897  cmp     edx, 11h
0x18001f89a  jb      short loc_18001F88B
0x18001f89c  jmp     short loc_18001F8A3
0x18001f89e  mov     ebx, 490h
0x18001f8a3  mov     eax, ebx
0x18001f8a5  mov     rcx, [rbp+57h+var_28]
0x18001f8a9  xor     rcx, rsp; StackCookie
0x18001f8ac  call    __security_check_cookie
0x18001f8b1  add     rsp, 88h
0x18001f8b8  pop     rdi
0x18001f8b9  pop     rsi
0x18001f8ba  pop     rbx
0x18001f8bb  pop     rbp
0x18001f8bc  retn
```
