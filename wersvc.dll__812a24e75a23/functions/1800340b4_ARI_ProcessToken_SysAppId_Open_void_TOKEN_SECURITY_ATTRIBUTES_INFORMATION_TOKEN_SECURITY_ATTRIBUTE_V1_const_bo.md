# ARI::ProcessToken::SysAppId::Open(void *,_TOKEN_SECURITY_ATTRIBUTES_INFORMATION * *,_TOKEN_SECURITY_ATTRIBUTE_V1 const * *,bool *)

- ea: `0x1800340b4`
- end: `0x18003424f`
- name: `?Open@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@PEAPEBU_TOKEN_SECURITY_ATTRIBUTE_V1@@PEA_N@Z`
- size: `411`
- prototype: `ULONG __fastcall(HANDLE TokenHandle, _QWORD *, const UNICODE_STRING **, const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033ea8`

## callees

- `0x1800035e8`
- `0x180033c44`
- `0x1800340b4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18003414d`
- `ntdll!RtlAllocateHeap` at `0x18003414d`
- `ntdll!NtQueryInformationToken` at `0x1800340f4`
- `ntdll!NtQueryInformationToken` at `0x18003418e`
- `ntdll!NtQueryInformationToken` at `0x1800340f4`
- `ntdll!NtQueryInformationToken` at `0x18003418e`
- `ntdll!RtlInitUnicodeString` at `0x1800341ce`
- `ntdll!RtlInitUnicodeString` at `0x1800341ce`
- `ntdll!RtlCompareUnicodeString` at `0x1800341f9`
- `ntdll!RtlCompareUnicodeString` at `0x1800341f9`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180034111`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003419a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180034111`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18003419a`

## pseudocode

```c
ULONG __fastcall ARI::ProcessToken::SysAppId::Open(
        HANDLE TokenHandle,
        _QWORD *a2,
        const UNICODE_STRING **a3,
        const struct _TOKEN_SECURITY_ATTRIBUTE_V1 **a4)
{
  NTSTATUS v7; // eax
  PVOID Heap; // rax
  _DWORD *v10; // rdi
  int v11; // eax
  ULONG v12; // ebx
  _DWORD *v13; // rsi
  __int64 v14; // rbx
  const UNICODE_STRING *v15; // rbp
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  __int128 v17; // [rsp+40h] [rbp-38h]
  ULONG Size; // [rsp+98h] [rbp+20h] BYREF
  int Size_4; // [rsp+9Ch] [rbp+24h]

  Size_4 = HIDWORD(a4);
  Size = 0;
  v7 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &Size);
  if ( v7 == -1073741789 )
  {
    *(_QWORD *)&DestinationString.Length = 0;
    if ( is_mul_ok(Size, 0x10u)
      && (Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, (Size * (unsigned __int128)0x10uLL) >> 64, 16LL * Size),
          (v10 = Heap) != 0) )
    {
      memset_0(Heap, 0, Size);
      v11 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, v10, Size, &Size);
      if ( v11 >= 0 )
      {
        v13 = v10 + 1;
        if ( v10[1]
          && (DestinationString = 0, RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID"), v14 = 0, v17 = 0, *v13) )
        {
          while ( 1 )
          {
            v15 = (const UNICODE_STRING *)(*((_QWORD *)v10 + 1) + 40 * v14);
            if ( !RtlCompareUnicodeString(&DestinationString, v15, 1u) )
              break;
            v14 = (unsigned int)(v14 + 1);
            if ( (unsigned int)v14 >= *v13 )
              goto LABEL_13;
          }
          *a3 = v15;
          *a2 = v10;
          ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(0);
          return 0;
        }
        else
        {
LABEL_13:
          ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(v10);
          return 1168;
        }
      }
      else
      {
        v12 = RtlNtStatusToDosErrorNoTeb(v11);
        ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(v10);
        return v12;
      }
    }
    else
    {
      ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(0);
      return 8;
    }
  }
  else if ( v7 )
  {
    return RtlNtStatusToDosErrorNoTeb(v7);
  }
  else
  {
    return 1359;
  }
}

```

## disassembly

```asm
0x1800340b4  mov     rax, rsp
0x1800340b7  mov     [rax+8], rbx
0x1800340bb  mov     [rax+10h], rbp
0x1800340bf  mov     [rax+20h], r9
0x1800340c3  push    rsi
0x1800340c4  push    rdi
0x1800340c5  push    r12
0x1800340c7  push    r14
0x1800340c9  push    r15
0x1800340cb  sub     rsp, 50h
0x1800340cf  xor     r9d, r9d; TokenInformationLength
0x1800340d2  mov     dword ptr [rax+20h], 0
0x1800340d9  mov     r15, r8
0x1800340dc  lea     rax, [rax+20h]
0x1800340e0  mov     r12, rdx
0x1800340e3  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x1800340e8  xor     r8d, r8d; TokenInformation
0x1800340eb  mov     rbx, rcx
0x1800340ee  lea     esi, [r9+27h]
0x1800340f2  mov     edx, esi; TokenInformationClass
0x1800340f4  call    cs:__imp_NtQueryInformationToken
0x1800340fa  cmp     eax, 0C0000023h
0x1800340ff  jz      short loc_18003411C
0x180034101  test    eax, eax
0x180034103  jnz     short loc_18003410F
0x180034105  mov     eax, 54Fh
0x18003410a  jmp     loc_180034236
0x18003410f  mov     ecx, eax; Status
0x180034111  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180034117  jmp     loc_180034236
0x18003411c  mov     ecx, dword ptr [rsp+78h+Size]
0x180034123  mov     eax, 10h
0x180034128  mul     rcx
0x18003412b  mov     qword ptr [rsp+78h+DestinationString.Length], 0
0x180034134  test    rdx, rdx
0x180034137  jnz     loc_18003422A
0x18003413d  mov     rcx, gs:60h
0x180034146  mov     r8, rax; Size
0x180034149  mov     rcx, [rcx+30h]; HeapHandle
0x18003414d  call    cs:__imp_RtlAllocateHeap
0x180034153  mov     rdi, rax
0x180034156  test    rax, rax
0x180034159  jz      loc_18003422A
0x18003415f  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x180034167  xor     edx, edx; Val
0x180034169  mov     rcx, rax; void *
0x18003416c  call    memset_0
0x180034171  mov     r9d, dword ptr [rsp+78h+Size]; TokenInformationLength
0x180034179  lea     rax, [rsp+78h+Size]
0x180034181  mov     r8, rdi; TokenInformation
0x180034184  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180034189  mov     edx, esi; TokenInformationClass
0x18003418b  mov     rcx, rbx; TokenHandle
0x18003418e  call    cs:__imp_NtQueryInformationToken
0x180034194  test    eax, eax
0x180034196  jns     short loc_1800341B1
0x180034198  mov     ecx, eax; Status
0x18003419a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800341a0  mov     rcx, rdi; P
0x1800341a3  mov     ebx, eax
0x1800341a5  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x1800341aa  mov     eax, ebx
0x1800341ac  jmp     loc_180034236
0x1800341b1  lea     rsi, [rdi+4]
0x1800341b5  cmp     dword ptr [rsi], 0
0x1800341b8  jbe     short loc_180034209
0x1800341ba  xorps   xmm0, xmm0
0x1800341bd  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x1800341c4  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x1800341c9  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x1800341ce  call    cs:__imp_RtlInitUnicodeString
0x1800341d4  xor     ebx, ebx
0x1800341d6  xorps   xmm0, xmm0
0x1800341d9  movups  [rsp+78h+var_38], xmm0
0x1800341de  cmp     [rsi], ebx
0x1800341e0  jbe     short loc_180034209
0x1800341e2  mov     rax, [rdi+8]
0x1800341e6  lea     rcx, [rbx+rbx*4]
0x1800341ea  mov     r8b, 1; CaseInsensitive
0x1800341ed  lea     rbp, [rax+rcx*8]
0x1800341f1  mov     rdx, rbp; String2
0x1800341f4  lea     rcx, [rsp+78h+DestinationString]; String1
0x1800341f9  call    cs:__imp_RtlCompareUnicodeString
0x1800341ff  test    eax, eax
0x180034201  jz      short loc_180034218
0x180034203  inc     ebx
0x180034205  cmp     ebx, [rsi]
0x180034207  jb      short loc_1800341E2
0x180034209  mov     rcx, rdi; P
0x18003420c  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x180034211  mov     eax, 490h
0x180034216  jmp     short loc_180034236
0x180034218  mov     [r15], rbp
0x18003421b  xor     ecx, ecx; P
0x18003421d  mov     [r12], rdi
0x180034221  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x180034226  xor     eax, eax
0x180034228  jmp     short loc_180034236
0x18003422a  xor     ecx, ecx; P
0x18003422c  call    ??$AutoPtrAriHeapDeallocate@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@ARI@@YAXPEAU_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@@Z; ARI::AutoPtrAriHeapDeallocate<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION>(_TOKEN_SECURITY_ATTRIBUTES_INFORMATION *)
0x180034231  mov     eax, 8
0x180034236  lea     r11, [rsp+78h+var_28]
0x18003423b  mov     rbx, [r11+30h]
0x18003423f  mov     rbp, [r11+38h]
0x180034243  mov     rsp, r11
0x180034246  pop     r15
0x180034248  pop     r14
0x18003424a  pop     r12
0x18003424c  pop     rdi
0x18003424d  pop     rsi
0x18003424e  retn
```
