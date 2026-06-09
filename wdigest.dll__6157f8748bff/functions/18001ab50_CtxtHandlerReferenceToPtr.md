# CtxtHandlerReferenceToPtr

- ea: `0x18001ab50`
- end: `0x18001accf`
- name: `CtxtHandlerReferenceToPtr`
- size: `383`
- prototype: `__int64 __fastcall(STRING *String1)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e4b0`

## callees

- `0x180011fec`
- `0x180018988`
- `0x18001a394`
- `0x18001ab50`

## import_xrefs

- `ntdll!RtlCompareString` at `0x18001abff`
- `ntdll!RtlCompareString` at `0x18001abff`
- `ntdll!RtlReleaseResource` at `0x18001ac11`
- `ntdll!RtlReleaseResource` at `0x18001ac27`
- `ntdll!RtlReleaseResource` at `0x18001ac11`
- `ntdll!RtlReleaseResource` at `0x18001ac27`
- `ntdll!RtlAcquireResourceShared` at `0x18001abcc`
- `ntdll!RtlAcquireResourceShared` at `0x18001abcc`

## pseudocode

```c
__int64 __fastcall CtxtHandlerReferenceToPtr(STRING *String1, struct _LIST_ENTRY near **a2)
{
  unsigned int v4; // edi
  struct _RTL_RESOURCE *v5; // rbp
  struct _LIST_ENTRY near **v6; // r15
  struct _LIST_ENTRY near *i; // rbx
  unsigned int v8; // edi
  PVOID *v9; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_aZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_96ced131d47a3bb15e65c6c6cb423035_Traceguids, String1);
  v4 = 0;
LABEL_5:
  if ( v4 >= 0x10 )
  {
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_aZ(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_96ced131d47a3bb15e65c6c6cb423035_Traceguids, String1);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    v8 = -1073741772;
  }
  else
  {
    v5 = (struct _RTL_RESOURCE *)&_ImageBase[48 * (v4 & (DigestContextLockCount - 1)) + 142176];
    RtlAcquireResourceShared(v5, 1u);
    v6 = &(&DigestContextList)[2 * v4];
    for ( i = *v6; ; i = i->Flink )
    {
      if ( i == (struct _LIST_ENTRY near *)v6 )
      {
        RtlReleaseResource(v5);
        ++v4;
        goto LABEL_5;
      }
      if ( (unsigned int)(HIDWORD(i[2].Blink) - 3) <= 1 && !RtlCompareString(String1, (const STRING *)&i[4], 0) )
        break;
    }
    v8 = 0;
    _InterlockedIncrement((volatile signed __int32 *)&i[1]);
    RtlReleaseResource(v5);
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        &WPP_96ced131d47a3bb15e65c6c6cb423035_Traceguids,
        i,
        i[1].Flink);
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    *a2 = i;
  }
  if ( v9 != &WPP_GLOBAL_Control && *((char *)v9 + 28) < 0 )
    WPP_SF_(v9[2], 34, &WPP_96ced131d47a3bb15e65c6c6cb423035_Traceguids);
  return v8;
}

```

## disassembly

```asm
0x18001ab50  push    rbx
0x18001ab52  push    rbp
0x18001ab53  push    rsi
0x18001ab54  push    rdi
0x18001ab55  push    r12
0x18001ab57  push    r14
0x18001ab59  push    r15
0x18001ab5b  sub     rsp, 30h
0x18001ab5f  mov     r14, rdx
0x18001ab62  mov     rsi, rcx
0x18001ab65  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ab6c  lea     r12, WPP_GLOBAL_Control
0x18001ab73  cmp     rcx, r12
0x18001ab76  jz      short loc_18001AB96
0x18001ab78  test    byte ptr [rcx+1Ch], 80h
0x18001ab7c  jz      short loc_18001AB96
0x18001ab7e  mov     rcx, [rcx+10h]
0x18001ab82  lea     r8, WPP_96ced131d47a3bb15e65c6c6cb423035_Traceguids
0x18001ab89  mov     edx, 1Eh
0x18001ab8e  mov     r9, rsi
0x18001ab91  call    WPP_SF_aZ
0x18001ab96  xor     edi, edi
0x18001ab98  lea     rbx, __ImageBase
0x18001ab9f  cmp     edi, 10h
0x18001aba2  jnb     loc_18001AC68
0x18001aba8  mov     ecx, cs:?DigestContextLockCount@@3KA; ulong DigestContextLockCount
0x18001abae  mov     dl, 1; Wait
0x18001abb0  dec     ecx
0x18001abb2  mov     eax, edi
0x18001abb4  and     rcx, rax
0x18001abb7  lea     rax, [rcx+rcx*2]
0x18001abbb  shl     rax, 5
0x18001abbf  lea     rbp, [rax+456C0h]
0x18001abc6  add     rbp, rbx
0x18001abc9  mov     rcx, rbp; Resource
0x18001abcc  call    cs:__imp_RtlAcquireResourceShared
0x18001abd2  lea     r15, rva ?DigestContextList@@3PAU_LIST_ENTRY@@A[rbx]; _LIST_ENTRY near * DigestContextList ...
0x18001abd9  mov     eax, edi
0x18001abdb  shl     rax, 4
0x18001abdf  add     r15, rax
0x18001abe2  mov     rbx, [r15]
0x18001abe5  cmp     rbx, r15
0x18001abe8  jz      short loc_18001AC0E
0x18001abea  mov     eax, [rbx+2Ch]
0x18001abed  sub     eax, 3
0x18001abf0  cmp     eax, 1
0x18001abf3  ja      short loc_18001AC09
0x18001abf5  lea     rdx, [rbx+40h]; String2
0x18001abf9  xor     r8d, r8d; CaseInSensitive
0x18001abfc  mov     rcx, rsi; String1
0x18001abff  call    cs:__imp_RtlCompareString
0x18001ac05  test    eax, eax
0x18001ac07  jz      short loc_18001AC1E
0x18001ac09  mov     rbx, [rbx]
0x18001ac0c  jmp     short loc_18001ABE5
0x18001ac0e  mov     rcx, rbp; Resource
0x18001ac11  call    cs:__imp_RtlReleaseResource
0x18001ac17  inc     edi
0x18001ac19  jmp     loc_18001AB98
0x18001ac1e  xor     edi, edi
0x18001ac20  lock inc dword ptr [rbx+10h]
0x18001ac24  mov     rcx, rbp; Resource
0x18001ac27  call    cs:__imp_RtlReleaseResource
0x18001ac2d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac34  cmp     rcx, r12
0x18001ac37  jz      short loc_18001AC63
0x18001ac39  test    byte ptr [rcx+1Ch], 4
0x18001ac3d  jz      short loc_18001AC63
0x18001ac3f  mov     eax, [rbx+10h]
0x18001ac42  lea     edx, [rdi+20h]
0x18001ac45  mov     rcx, [rcx+10h]
0x18001ac49  lea     r8, WPP_96ced131d47a3bb15e65c6c6cb423035_Traceguids
0x18001ac50  mov     r9, rbx
0x18001ac53  mov     [rsp+68h+var_48], eax
0x18001ac57  call    WPP_SF_qD
0x18001ac5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac63  mov     [r14], rbx
0x18001ac66  jmp     short loc_18001AC9E
0x18001ac68  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac6f  cmp     rcx, r12
0x18001ac72  jz      short loc_18001AC99
0x18001ac74  test    byte ptr [rcx+1Ch], 2
0x18001ac78  jz      short loc_18001AC99
0x18001ac7a  mov     rcx, [rcx+10h]
0x18001ac7e  lea     r8, WPP_96ced131d47a3bb15e65c6c6cb423035_Traceguids
0x18001ac85  mov     edx, 21h ; '!'
0x18001ac8a  mov     r9, rsi
0x18001ac8d  call    WPP_SF_aZ
0x18001ac92  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac99  mov     edi, 0C0000034h
0x18001ac9e  cmp     rcx, r12
0x18001aca1  jz      short loc_18001ACBE
0x18001aca3  test    byte ptr [rcx+1Ch], 80h
0x18001aca7  jz      short loc_18001ACBE
0x18001aca9  mov     rcx, [rcx+10h]
0x18001acad  lea     r8, WPP_96ced131d47a3bb15e65c6c6cb423035_Traceguids
0x18001acb4  mov     edx, 22h ; '"'
0x18001acb9  call    WPP_SF_
0x18001acbe  mov     eax, edi
0x18001acc0  add     rsp, 30h
0x18001acc4  pop     r15
0x18001acc6  pop     r14
0x18001acc8  pop     r12
0x18001acca  pop     rdi
0x18001accb  pop     rsi
0x18001accc  pop     rbp
0x18001accd  pop     rbx
0x18001acce  retn
```
