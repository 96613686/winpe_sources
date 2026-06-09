# ValidateSecurityQOS(_RPC_SECURITY_QOS *,int,ushort *)

- ea: `0x180067660`
- end: `0x180067770`
- name: `?ValidateSecurityQOS@@YAJPEAU_RPC_SECURITY_QOS@@HPEAG@Z`
- size: `272`
- prototype: `__int64 __fastcall(struct _RPC_SECURITY_QOS *, int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800674d0`
- `0x180067e00`

## callees

- `0x180067660`
- `0x18009c8f8`
- `0x18009e5a4`

## import_xrefs

- `ntdll!RtlValidSecurityDescriptor` at `0x180067718`
- `ntdll!RtlValidSecurityDescriptor` at `0x180067718`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800676ea`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800676ea`

## pseudocode

```c
__int64 __fastcall ValidateSecurityQOS(struct _RPC_SECURITY_QOS *a1, int a2, unsigned __int16 *a3)
{
  unsigned int Version; // ecx
  unsigned int v6; // eax
  __int64 v7; // rsi
  void *v8; // rcx
  __int64 result; // rax
  void *v10; // rcx
  void *v11; // rcx

  Version = a1->Version;
  if ( Version - 1 > 4 || a1->IdentityTracking > 1 || a1->ImpersonationType > 4 || (a1->Capabilities & 0xFFFFFFC2) != 0 )
    return 87;
  v6 = a1->Capabilities & 1;
  if ( (a1->Capabilities & 0x10) != 0 )
  {
    if ( !v6 || a2 )
      return 87;
  }
  else if ( !v6 )
  {
    goto LABEL_12;
  }
  if ( a3 && *a3 )
  {
LABEL_12:
    if ( Version <= 1 )
      return 0;
    goto LABEL_13;
  }
  if ( Version < 3 || !*(_QWORD *)&a1[2].Version )
    return 87;
LABEL_13:
  v7 = *(_QWORD *)&a1[1].IdentityTracking;
  if ( a1[1].Version != 1 )
  {
    if ( a1[1].Version || v7 )
      return 87;
    goto LABEL_16;
  }
  if ( !v7 )
    return 87;
  result = ValidateHttpCredentialsCommon(*(struct _RPC_HTTP_TRANSPORT_CREDENTIALS_W **)&a1[1].IdentityTracking);
  if ( !(_DWORD)result )
  {
    if ( !*(_QWORD *)v7 || (result = ValidateAuthIdentity(*(void **)v7), !(_DWORD)result) )
    {
      if ( (*(_BYTE *)(v7 + 12) & 2) == 0
        || (v11 = *(void **)(v7 + 40)) == 0
        || (result = ValidateAuthIdentity(v11), !(_DWORD)result) )
      {
LABEL_16:
        if ( a1->Version < 3 || (v8 = *(void **)&a1[2].Version) == 0 || !a2 && IsValidSid(v8) )
        {
          if ( a1->Version < 5 )
            return 0;
          v10 = *(void **)&a1[3].Version;
          if ( !v10 || RtlValidSecurityDescriptor(v10) )
            return 0;
        }
        return 87;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180067660  push    rbx
0x180067662  push    rbp
0x180067663  push    rsi
0x180067664  push    rdi
0x180067665  sub     rsp, 28h
0x180067669  mov     rdi, rcx
0x18006766c  mov     ebp, edx
0x18006766e  mov     ecx, [rcx]
0x180067670  lea     eax, [rcx-1]
0x180067673  cmp     eax, 4
0x180067676  ja      loc_180067708
0x18006767c  cmp     dword ptr [rdi+8], 1
0x180067680  ja      loc_180067708
0x180067686  cmp     dword ptr [rdi+0Ch], 4
0x18006768a  ja      short loc_180067708
0x18006768c  test    dword ptr [rdi+4], 0FFFFFFC2h
0x180067693  jnz     short loc_180067708
0x180067695  mov     eax, [rdi+4]
0x180067698  xor     ebx, ebx
0x18006769a  and     eax, 1
0x18006769d  test    byte ptr [rdi+4], 10h
0x1800676a1  jnz     short loc_180067704
0x1800676a3  test    eax, eax
0x1800676a5  jz      short loc_1800676BF
0x1800676a7  test    r8, r8
0x1800676aa  jnz     short loc_1800676B9
0x1800676ac  cmp     ecx, 3
0x1800676af  jb      short loc_180067708
0x1800676b1  cmp     [rdi+20h], rbx
0x1800676b5  jz      short loc_180067708
0x1800676b7  jmp     short loc_1800676C4
0x1800676b9  cmp     [r8], bx
0x1800676bd  jz      short loc_1800676AC
0x1800676bf  cmp     ecx, 1
0x1800676c2  jbe     short loc_1800676F9
0x1800676c4  cmp     dword ptr [rdi+10h], 1
0x1800676c8  mov     rsi, [rdi+18h]
0x1800676cc  jz      short loc_18006772D
0x1800676ce  cmp     [rdi+10h], ebx
0x1800676d1  jnz     short loc_180067708
0x1800676d3  test    rsi, rsi
0x1800676d6  jnz     short loc_180067708
0x1800676d8  cmp     dword ptr [rdi], 3
0x1800676db  jb      short loc_1800676F4
0x1800676dd  mov     rcx, [rdi+20h]; pSid
0x1800676e1  test    rcx, rcx
0x1800676e4  jz      short loc_1800676F4
0x1800676e6  test    ebp, ebp
0x1800676e8  jnz     short loc_180067708
0x1800676ea  call    cs:__imp_IsValidSid
0x1800676f0  test    eax, eax
0x1800676f2  jz      short loc_180067708
0x1800676f4  cmp     dword ptr [rdi], 5
0x1800676f7  jnb     short loc_18006770F
0x1800676f9  xor     eax, eax
0x1800676fb  add     rsp, 28h
0x1800676ff  pop     rdi
0x180067700  pop     rsi
0x180067701  pop     rbp
0x180067702  pop     rbx
0x180067703  retn
0x180067704  test    eax, eax
0x180067706  jnz     short loc_180067724
0x180067708  mov     eax, 57h ; 'W'
0x18006770d  jmp     short loc_1800676FB
0x18006770f  mov     rcx, [rdi+30h]; SecurityDescriptor
0x180067713  test    rcx, rcx
0x180067716  jz      short loc_1800676F9
0x180067718  call    cs:__imp_RtlValidSecurityDescriptor
0x18006771e  test    al, al
0x180067720  jz      short loc_180067708
0x180067722  jmp     short loc_1800676F9
0x180067724  test    ebp, ebp
0x180067726  jnz     short loc_180067708
0x180067728  jmp     loc_1800676A7
0x18006772d  test    rsi, rsi
0x180067730  jz      short loc_180067708
0x180067732  mov     rcx, rsi; struct _RPC_HTTP_TRANSPORT_CREDENTIALS_W *
0x180067735  call    ?ValidateHttpCredentialsCommon@@YAJPEAU_RPC_HTTP_TRANSPORT_CREDENTIALS_W@@@Z; ValidateHttpCredentialsCommon(_RPC_HTTP_TRANSPORT_CREDENTIALS_W *)
0x18006773a  test    eax, eax
0x18006773c  jnz     short loc_1800676FB
0x18006773e  cmp     [rsi], rbx
0x180067741  jz      short loc_18006774F
0x180067743  mov     rcx, [rsi]; void *
0x180067746  call    ?ValidateAuthIdentity@@YAJPEAX@Z; ValidateAuthIdentity(void *)
0x18006774b  test    eax, eax
0x18006774d  jnz     short loc_1800676FB
0x18006774f  test    byte ptr [rsi+0Ch], 2
0x180067753  jz      short loc_1800676D8
0x180067755  mov     rcx, [rsi+28h]; void *
0x180067759  test    rcx, rcx
0x18006775c  jz      loc_1800676D8
0x180067762  call    ?ValidateAuthIdentity@@YAJPEAX@Z; ValidateAuthIdentity(void *)
0x180067767  test    eax, eax
0x180067769  jnz     short loc_1800676FB
0x18006776b  jmp     loc_1800676D8
```
