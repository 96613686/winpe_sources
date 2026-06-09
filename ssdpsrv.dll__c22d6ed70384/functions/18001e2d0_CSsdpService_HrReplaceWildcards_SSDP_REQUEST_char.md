# CSsdpService::HrReplaceWildcards(_SSDP_REQUEST *,char *)

- ea: `0x18001e2d0`
- end: `0x18001e3bb`
- name: `?HrReplaceWildcards@CSsdpService@@IEAAJPEAU_SSDP_REQUEST@@PEAD@Z`
- size: `235`
- prototype: `__int64 __fastcall(CSsdpService *this, const struct _GUID *, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800029b0`

## callees

- `0x180010654`
- `0x18001e2d0`
- `0x180026a30`
- `0x18002fe08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18001e2fe`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18001e2fe`

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
0x18001e2d0  push    rbp
0x18001e2d2  push    rbx
0x18001e2d3  push    rsi
0x18001e2d4  push    rdi
0x18001e2d5  lea     rbp, [rsp-3Fh]
0x18001e2da  sub     rsp, 88h
0x18001e2e1  mov     rax, cs:__security_cookie
0x18001e2e8  xor     rax, rsp
0x18001e2eb  mov     [rbp+57h+var_28], rax
0x18001e2ef  mov     rsi, rdx
0x18001e2f2  mov     rcx, r8; Str
0x18001e2f5  lea     rdx, aSsdpmacaddress; "%SSDPMACADDRESS_%"
0x18001e2fc  xor     ebx, ebx
0x18001e2fe  call    cs:__imp_strstr
0x18001e304  mov     rdi, rax
0x18001e307  test    rax, rax
0x18001e30a  jz      loc_18001E3A1
0x18001e310  lea     rdx, [rsi+20h]; struct _GUID *
0x18001e314  mov     [rbp+57h+var_50], 8
0x18001e31b  lea     r9, [rbp+57h+var_50]; unsigned int *
0x18001e31f  lea     r8, [rbp+57h+var_48]; unsigned __int8 *
0x18001e323  lea     rcx, ?s_instance@CInterfaceHelper@@0V1@A; this
0x18001e32a  call    ?HrGetPhysicalAddress@CInterfaceHelper@@QEAAJAEBU_GUID@@PEAEPEAK@Z; CInterfaceHelper::HrGetPhysicalAddress(_GUID const &,uchar *,ulong *)
0x18001e32f  mov     ebx, eax
0x18001e331  test    eax, eax
0x18001e333  js      short loc_18001E3A1
0x18001e335  cmp     [rbp+57h+var_50], 6
0x18001e339  jb      short loc_18001E39C
0x18001e33b  movzx   eax, [rbp+57h+var_43]
0x18001e33f  movzx   ecx, [rbp+57h+var_44]
0x18001e343  movzx   edx, [rbp+57h+var_45]
0x18001e347  movzx   r8d, [rbp+57h+var_46]
0x18001e34c  movzx   r10d, [rbp+57h+var_47]
0x18001e351  movzx   r9d, [rbp+57h+var_48]
0x18001e356  mov     [rsp+0A0h+var_60], eax
0x18001e35a  mov     [rsp+0A0h+var_68], ecx
0x18001e35e  lea     rcx, [rbp+57h+var_40]; char *
0x18001e362  mov     [rsp+0A0h+var_70], edx
0x18001e366  mov     edx, 12h; unsigned __int64
0x18001e36b  mov     [rsp+0A0h+var_78], r8d
0x18001e370  lea     r8, a02x02x02x02x02; "%02x:%02x:%02x:%02x:%02x:%02x"
0x18001e377  mov     [rsp+0A0h+var_80], r10d
0x18001e37c  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001e381  mov     ebx, eax
0x18001e383  test    eax, eax
0x18001e385  js      short loc_18001E3A1
0x18001e387  xor     edx, edx
0x18001e389  movsxd  rcx, edx
0x18001e38c  inc     edx
0x18001e38e  mov     al, [rbp+rcx+57h+var_40]
0x18001e392  mov     [rcx+rdi], al
0x18001e395  cmp     edx, 11h
0x18001e398  jb      short loc_18001E389
0x18001e39a  jmp     short loc_18001E3A1
0x18001e39c  mov     ebx, 490h
0x18001e3a1  mov     eax, ebx
0x18001e3a3  mov     rcx, [rbp+57h+var_28]
0x18001e3a7  xor     rcx, rsp; StackCookie
0x18001e3aa  call    __security_check_cookie
0x18001e3af  add     rsp, 88h
0x18001e3b6  pop     rdi
0x18001e3b7  pop     rsi
0x18001e3b8  pop     rbx
0x18001e3b9  pop     rbp
0x18001e3ba  retn
```
