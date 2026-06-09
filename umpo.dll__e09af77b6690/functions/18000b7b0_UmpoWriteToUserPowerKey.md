# UmpoWriteToUserPowerKey

- ea: `0x18000b7b0`
- end: `0x18000b9b0`
- name: `UmpoWriteToUserPowerKey`
- size: `512`
- prototype: `__int64 __fastcall(UUID *Uuid1, UUID *, UUID *, unsigned int, DWORD dwType, BYTE *, DWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000c780`

## callees

- `0x180007790`
- `0x18000b7b0`
- `0x18000b9b8`
- `0x180010070`

## import_xrefs

- `RPCRT4!UuidEqual` at `0x18000b865`
- `RPCRT4!UuidEqual` at `0x18000b865`

## pseudocode

```c
__int64 __fastcall UmpoWriteToUserPowerKey(
        UUID *Uuid1,
        UUID *a2,
        UUID *a3,
        unsigned int a4,
        DWORD dwType,
        BYTE *a6,
        DWORD a7)
{
  GUID *v9; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned int v14; // esi
  int i; // ebp
  unsigned int v16; // ebx
  RPC_STATUS Status; // [rsp+40h] [rbp-78h] BYREF
  _DWORD v18[3]; // [rsp+44h] [rbp-74h] BYREF
  __int64 v19[2]; // [rsp+50h] [rbp-68h] BYREF

  *(_QWORD *)&v18[1] = a6;
  Status = 0;
  v9 = Uuid1;
  *(_OWORD *)v19 = 0;
  if ( a4 > 3 && a4 != 13 )
    return 87;
  if ( !UmpoFullPowerPlanSupportDisabled )
  {
    if ( Uuid1 )
      goto LABEL_6;
    return UmpoInternalWriteToUserPowerKeyEx((__int64)v9, a2, a3, dwType, a6, a7);
  }
  if ( a4 >= 2 )
    return 50;
  if ( !Uuid1 )
    return UmpoInternalWriteToUserPowerKeyEx((__int64)v9, a2, a3, dwType, a6, a7);
  v11 = *(_QWORD *)&Uuid1->Data1 - *(_QWORD *)&GUID_TYPICAL_POWER_SAVINGS.Data1;
  if ( *(_QWORD *)&Uuid1->Data1 == *(_QWORD *)&GUID_TYPICAL_POWER_SAVINGS.Data1 )
    v11 = *(_QWORD *)Uuid1->Data4 - *(_QWORD *)GUID_TYPICAL_POWER_SAVINGS.Data4;
  if ( v11 )
  {
    v12 = *(_QWORD *)&Uuid1->Data1 - *(_QWORD *)&ALL_POWERSCHEMES_GUID.Data1;
    if ( *(_QWORD *)&Uuid1->Data1 == *(_QWORD *)&ALL_POWERSCHEMES_GUID.Data1 )
      v12 = *(_QWORD *)Uuid1->Data4 - *(_QWORD *)ALL_POWERSCHEMES_GUID.Data4;
    if ( v12 )
      return 50;
  }
  v13 = *(_QWORD *)&Uuid1->Data1 - *(_QWORD *)&ALL_POWERSCHEMES_GUID.Data1;
  if ( *(_QWORD *)&Uuid1->Data1 == *(_QWORD *)&ALL_POWERSCHEMES_GUID.Data1 )
    v13 = *(_QWORD *)Uuid1->Data4 - *(_QWORD *)ALL_POWERSCHEMES_GUID.Data4;
  if ( !v13 )
    v9 = &GUID_TYPICAL_POWER_SAVINGS;
LABEL_6:
  if ( !UuidEqual(v9, (UUID *)&ALL_POWERSCHEMES_GUID, &Status) )
    return UmpoInternalWriteToUserPowerKeyEx((__int64)v9, a2, a3, dwType, a6, a7);
  v14 = 0;
  for ( i = 0; ; ++i )
  {
    v18[0] = 16;
    v16 = UmpoEnumerate(0, 0, (__int64)v19, (__int64)v18, 1);
    if ( !v16 )
    {
      v14 = UmpoInternalWriteToUserPowerKeyEx((__int64)v19, a2, a3, dwType, *(BYTE **)&v18[1], a7);
      if ( v14 )
        break;
    }
    if ( v16 )
    {
      if ( v16 != 259 )
        return v16;
      return v14;
    }
  }
  return v14;
}

```

## disassembly

```asm
0x18000b7b0  push    rbx
0x18000b7b2  push    rbp
0x18000b7b3  push    rsi
0x18000b7b4  push    rdi
0x18000b7b5  push    r12
0x18000b7b7  push    r13
0x18000b7b9  push    r14
0x18000b7bb  push    r15
0x18000b7bd  sub     rsp, 78h
0x18000b7c1  mov     rax, cs:__security_cookie
0x18000b7c8  xor     rax, rsp
0x18000b7cb  mov     [rsp+0B8h+var_58], rax
0x18000b7d0  mov     rsi, [rsp+0B8h+arg_28]
0x18000b7d8  xorps   xmm0, xmm0
0x18000b7db  mov     qword ptr [rsp+0B8h+var_74+4], rsi
0x18000b7e0  mov     edi, r9d
0x18000b7e3  mov     [rsp+0B8h+Status], 0
0x18000b7eb  mov     r13, r8
0x18000b7ee  mov     r12, rdx
0x18000b7f1  mov     rbx, rcx
0x18000b7f4  movups  xmmword ptr [rsp+0B8h+var_68], xmm0
0x18000b7f9  cmp     r9d, 3
0x18000b7fd  ja      loc_18000B8A1
0x18000b803  cmp     cs:UmpoFullPowerPlanSupportDisabled, 0
0x18000b80a  jz      short loc_18000B851
0x18000b80c  mov     ecx, edi
0x18000b80e  test    edi, edi
0x18000b810  jz      loc_18000B8B1
0x18000b816  sub     ecx, 1
0x18000b819  jz      loc_18000B8B1
0x18000b81f  sub     ecx, 1
0x18000b822  jz      short loc_18000B82E
0x18000b824  sub     ecx, 1
0x18000b827  jz      short loc_18000B82E
0x18000b829  cmp     ecx, 0Ah
0x18000b82c  jnz     short loc_18000B851
0x18000b82e  mov     eax, 32h ; '2'
0x18000b833  mov     rcx, [rsp+0B8h+var_58]
0x18000b838  xor     rcx, rsp; StackCookie
0x18000b83b  call    __security_check_cookie
0x18000b840  add     rsp, 78h
0x18000b844  pop     r15
0x18000b846  pop     r14
0x18000b848  pop     r13
0x18000b84a  pop     r12
0x18000b84c  pop     rdi
0x18000b84d  pop     rsi
0x18000b84e  pop     rbp
0x18000b84f  pop     rbx
0x18000b850  retn
0x18000b851  test    rbx, rbx
0x18000b854  jz      short loc_18000B873
0x18000b856  lea     r8, [rsp+0B8h+Status]; Status
0x18000b85b  mov     rcx, rbx; Uuid1
0x18000b85e  lea     rdx, ALL_POWERSCHEMES_GUID; Uuid2
0x18000b865  call    cs:__imp_UuidEqual
0x18000b86b  test    eax, eax
0x18000b86d  jnz     loc_18000B91C
0x18000b873  mov     eax, [rsp+0B8h+arg_30]
0x18000b87a  mov     r9d, edi
0x18000b87d  mov     [rsp+0B8h+var_88], eax; DWORD
0x18000b881  mov     r8, r13; Uuid2
0x18000b884  mov     eax, [rsp+0B8h+arg_20]
0x18000b88b  mov     rdx, r12; Uuid1
0x18000b88e  mov     [rsp+0B8h+var_90], rsi; BYTE *
0x18000b893  mov     rcx, rbx; __int64
0x18000b896  mov     [rsp+0B8h+dwType], eax; dwType
0x18000b89a  call    UmpoInternalWriteToUserPowerKeyEx
0x18000b89f  jmp     short loc_18000B833
0x18000b8a1  cmp     edi, 0Dh
0x18000b8a4  jz      loc_18000B803
0x18000b8aa  mov     eax, 57h ; 'W'
0x18000b8af  jmp     short loc_18000B833
0x18000b8b1  test    rbx, rbx
0x18000b8b4  jz      short loc_18000B873
0x18000b8b6  mov     rax, [rbx]
0x18000b8b9  sub     rax, qword ptr cs:GUID_TYPICAL_POWER_SAVINGS.Data1
0x18000b8c0  jnz     short loc_18000B8CD
0x18000b8c2  mov     rax, [rbx+8]
0x18000b8c6  sub     rax, qword ptr cs:GUID_TYPICAL_POWER_SAVINGS.Data4
0x18000b8cd  mov     rdx, qword ptr cs:ALL_POWERSCHEMES_GUID.Data4
0x18000b8d4  mov     rcx, qword ptr cs:ALL_POWERSCHEMES_GUID.Data1
0x18000b8db  test    rax, rax
0x18000b8de  jz      short loc_18000B8F8
0x18000b8e0  mov     rax, [rbx]
0x18000b8e3  sub     rax, rcx
0x18000b8e6  jnz     short loc_18000B8EF
0x18000b8e8  mov     rax, [rbx+8]
0x18000b8ec  sub     rax, rdx
0x18000b8ef  test    rax, rax
0x18000b8f2  jnz     loc_18000B82E
0x18000b8f8  mov     rax, [rbx]
0x18000b8fb  sub     rax, rcx
0x18000b8fe  jnz     short loc_18000B907
0x18000b900  mov     rax, [rbx+8]
0x18000b904  sub     rax, rdx
0x18000b907  test    rax, rax
0x18000b90a  jnz     loc_18000B856
0x18000b910  lea     rbx, GUID_TYPICAL_POWER_SAVINGS
0x18000b917  jmp     loc_18000B856
0x18000b91c  mov     r14d, [rsp+0B8h+arg_30]
0x18000b924  xor     esi, esi
0x18000b926  mov     r15d, [rsp+0B8h+arg_20]
0x18000b92e  xor     ebp, ebp
0x18000b930  xor     edx, edx; UUID *
0x18000b932  mov     byte ptr [rsp+0B8h+var_88], 1; char
0x18000b937  lea     rax, [rsp+0B8h+var_74]
0x18000b93c  mov     dword ptr [rsp+0B8h+var_74], 10h
0x18000b944  mov     [rsp+0B8h+var_90], rax; __int64
0x18000b949  mov     r9d, ebp
0x18000b94c  lea     rax, [rsp+0B8h+var_68]
0x18000b951  xor     ecx, ecx; Uuid2
0x18000b953  lea     r8d, [rdx+10h]
0x18000b957  mov     qword ptr [rsp+0B8h+dwType], rax; __int64
0x18000b95c  call    UmpoEnumerate
0x18000b961  mov     ebx, eax
0x18000b963  test    eax, eax
0x18000b965  jnz     short loc_18000B994
0x18000b967  mov     rax, qword ptr [rsp+0B8h+var_74+4]
0x18000b96c  lea     rcx, [rsp+0B8h+var_68]; __int64
0x18000b971  mov     [rsp+0B8h+var_88], r14d; DWORD
0x18000b976  mov     r9d, edi
0x18000b979  mov     [rsp+0B8h+var_90], rax; BYTE *
0x18000b97e  mov     r8, r13; Uuid2
0x18000b981  mov     rdx, r12; Uuid1
0x18000b984  mov     [rsp+0B8h+dwType], r15d; dwType
0x18000b989  call    UmpoInternalWriteToUserPowerKeyEx
0x18000b98e  mov     esi, eax
0x18000b990  test    eax, eax
0x18000b992  jnz     short loc_18000B9A9
0x18000b994  inc     ebp
0x18000b996  test    ebx, ebx
0x18000b998  jz      short loc_18000B930
0x18000b99a  cmp     ebx, 103h
0x18000b9a0  jz      short loc_18000B9A9
0x18000b9a2  mov     eax, ebx
0x18000b9a4  jmp     loc_18000B833
0x18000b9a9  mov     eax, esi
0x18000b9ab  jmp     loc_18000B833
```
