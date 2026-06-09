# AppendAllowedAceToSelfRelativeSD

- ea: `0x180026fd4`
- end: `0x1800271be`
- name: `AppendAllowedAceToSelfRelativeSD`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000aa8c`

## callees

- `0x180026fd4`
- `0x1800435f8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800270d1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800270d1`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180027124`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x180027124`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800270ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027161`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800270ea`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027161`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027191`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800271a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027191`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800271a4`
- `ntdll!RtlMakeSelfRelativeSD` at `0x180027151`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18002717a`
- `ntdll!RtlMakeSelfRelativeSD` at `0x180027151`
- `ntdll!RtlMakeSelfRelativeSD` at `0x18002717a`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18002713a`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18002713a`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18002701f`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18002701f`

## pseudocode

```c
char __fastcall AppendAllowedAceToSelfRelativeSD(__int64 a1, DWORD a2, void *a3, __int64 a4, _QWORD *a5)
{
  char result; // al
  char v9; // r14
  __int16 v10; // cx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned __int16 *v14; // rdi
  DWORD v15; // r15d
  struct _ACL *v16; // rax
  struct _ACL *v17; // rsi
  void *v18; // rbx
  HLOCAL v19; // rax
  __int128 SecurityDescriptor; // [rsp+30h] [rbp-38h] BYREF
  __int128 v21; // [rsp+40h] [rbp-28h]
  __int64 v22; // [rsp+50h] [rbp-18h]
  ULONG BufferLength; // [rsp+B0h] [rbp+48h] BYREF

  result = 0;
  SecurityDescriptor = 0;
  v22 = 0;
  v21 = 0;
  BufferLength = 0;
  if ( *(__int16 *)(a4 + 2) < 0 )
  {
    v9 = 0;
    if ( RtlCreateSecurityDescriptor(&SecurityDescriptor, 1u) < 0 )
      return v9;
    v10 = *(_WORD *)(a4 + 2);
    WORD1(SecurityDescriptor) = v10 & 0x7FFF;
    if ( v10 >= 0 )
    {
      v11 = *(_QWORD *)(a4 + 8);
    }
    else
    {
      if ( !*(_DWORD *)(a4 + 4) )
        goto LABEL_10;
      v11 = a4 + *(unsigned int *)(a4 + 4);
    }
    if ( v11 )
      *((_QWORD *)&SecurityDescriptor + 1) = v11;
    if ( v10 >= 0 )
    {
      v12 = *(_QWORD *)(a4 + 16);
      goto LABEL_13;
    }
LABEL_10:
    if ( !*(_DWORD *)(a4 + 8) )
      goto LABEL_15;
    v12 = a4 + *(unsigned int *)(a4 + 8);
LABEL_13:
    if ( v12 )
      *(_QWORD *)&v21 = v12;
LABEL_15:
    if ( (v10 & 0x10) == 0 )
      goto LABEL_22;
    if ( v10 >= 0 )
    {
      v13 = *(_QWORD *)(a4 + 24);
    }
    else
    {
      if ( !*(_DWORD *)(a4 + 12) )
        goto LABEL_22;
      v13 = a4 + *(unsigned int *)(a4 + 12);
    }
    if ( v13 )
      *((_QWORD *)&v21 + 1) = v13;
LABEL_22:
    if ( (v10 & 4) != 0 )
    {
      if ( v10 >= 0 )
      {
        v14 = *(unsigned __int16 **)(a4 + 32);
        goto LABEL_27;
      }
      if ( *(_DWORD *)(a4 + 16) )
      {
        v14 = (unsigned __int16 *)(a4 + *(unsigned int *)(a4 + 16));
LABEL_27:
        if ( v14 )
        {
          v15 = v14[1] + GetLengthSid(a3) + 12;
          v16 = (struct _ACL *)LocalAlloc(0x40u, v15);
          v17 = v16;
          if ( v16 )
          {
            v18 = 0;
            memcpy_0(v16, v14, v14[1]);
            v17->AclSize = v15;
            if ( AddAccessAllowedAceEx(v17, 2u, 0, a2, a3) )
            {
              if ( RtlSetDaclSecurityDescriptor(&SecurityDescriptor, 1u, v17, 0) >= 0 )
              {
                BufferLength = 0;
                if ( RtlMakeSelfRelativeSD(&SecurityDescriptor, 0, &BufferLength) < 0 )
                {
                  v19 = LocalAlloc(0x40u, BufferLength);
                  v18 = v19;
                  if ( v19 )
                  {
                    if ( RtlMakeSelfRelativeSD(&SecurityDescriptor, v19, &BufferLength) >= 0 )
                    {
                      v9 = 1;
                      *a5 = v18;
                    }
                  }
                }
              }
            }
            LocalFree(v17);
            if ( !v9 )
            {
              if ( v18 )
                LocalFree(v18);
            }
          }
        }
      }
    }
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180026fd4  mov     [rsp-40h+BufferLength], ecx
0x180026fd8  push    rbp
0x180026fd9  push    rbx
0x180026fda  push    rsi
0x180026fdb  push    rdi
0x180026fdc  push    r12
0x180026fde  push    r13
0x180026fe0  push    r14
0x180026fe2  push    r15
0x180026fe4  mov     rbp, rsp
0x180026fe7  sub     rsp, 68h
0x180026feb  xor     eax, eax
0x180026fed  xor     esi, esi
0x180026fef  xorps   xmm0, xmm0
0x180026ff2  mov     rbx, r9
0x180026ff5  mov     r12, r8
0x180026ff8  mov     r13d, edx
0x180026ffb  movups  [rbp+SecurityDescriptor], xmm0
0x180026fff  mov     [rbp+var_18], rax
0x180027003  movups  [rbp+var_28], xmm0
0x180027007  mov     [rbp+BufferLength], esi
0x18002700a  cmp     [r9+2], si
0x18002700f  jge     loc_1800271AD
0x180027015  lea     edx, [rax+1]; Revision
0x180027018  mov     r14b, sil
0x18002701b  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18002701f  call    cs:__imp_RtlCreateSecurityDescriptor
0x180027025  test    eax, eax
0x180027027  js      loc_1800271AA
0x18002702d  movzx   ecx, word ptr [rbx+2]
0x180027031  mov     edx, 7FFFh
0x180027036  movzx   eax, cx
0x180027039  and     ax, dx
0x18002703c  mov     word ptr [rbp+SecurityDescriptor+2], ax
0x180027040  test    cx, cx
0x180027043  jns     short loc_180027052
0x180027045  cmp     [rbx+4], esi
0x180027048  jz      short loc_180027064
0x18002704a  mov     eax, [rbx+4]
0x18002704d  add     rax, rbx
0x180027050  jmp     short loc_180027056
0x180027052  mov     rax, [rbx+8]
0x180027056  test    rax, rax
0x180027059  jz      short loc_18002705F
0x18002705b  mov     qword ptr [rbp+SecurityDescriptor+8], rax
0x18002705f  test    cx, cx
0x180027062  jns     short loc_180027071
0x180027064  cmp     [rbx+8], esi
0x180027067  jz      short loc_18002707E
0x180027069  mov     eax, [rbx+8]
0x18002706c  add     rax, rbx
0x18002706f  jmp     short loc_180027075
0x180027071  mov     rax, [rbx+10h]
0x180027075  test    rax, rax
0x180027078  jz      short loc_18002707E
0x18002707a  mov     qword ptr [rbp+var_28], rax
0x18002707e  test    cl, 10h
0x180027081  jz      short loc_1800270A2
0x180027083  test    cx, cx
0x180027086  jns     short loc_180027095
0x180027088  cmp     [rbx+0Ch], esi
0x18002708b  jz      short loc_1800270A2
0x18002708d  mov     eax, [rbx+0Ch]
0x180027090  add     rax, rbx
0x180027093  jmp     short loc_180027099
0x180027095  mov     rax, [rbx+18h]
0x180027099  test    rax, rax
0x18002709c  jz      short loc_1800270A2
0x18002709e  mov     qword ptr [rbp+var_28+8], rax
0x1800270a2  test    cl, 4
0x1800270a5  jz      loc_1800271AA
0x1800270ab  test    cx, cx
0x1800270ae  jns     short loc_1800270C1
0x1800270b0  cmp     [rbx+10h], esi
0x1800270b3  jz      loc_1800271AA
0x1800270b9  mov     edi, [rbx+10h]
0x1800270bc  add     rdi, rbx
0x1800270bf  jmp     short loc_1800270C5
0x1800270c1  mov     rdi, [rbx+20h]
0x1800270c5  test    rdi, rdi
0x1800270c8  jz      loc_1800271AA
0x1800270ce  mov     rcx, r12; pSid
0x1800270d1  call    cs:__imp_GetLengthSid
0x1800270d7  movzx   ecx, word ptr [rdi+2]
0x1800270db  lea     r15d, [rax+0Ch]
0x1800270df  add     r15d, ecx
0x1800270e2  mov     ecx, 40h ; '@'; uFlags
0x1800270e7  mov     edx, r15d; uBytes
0x1800270ea  call    cs:__imp_LocalAlloc
0x1800270f0  mov     rsi, rax
0x1800270f3  test    rax, rax
0x1800270f6  jz      loc_1800271AA
0x1800270fc  movzx   r8d, word ptr [rdi+2]; Size
0x180027101  mov     rdx, rdi; Src
0x180027104  mov     rcx, rax; void *
0x180027107  xor     ebx, ebx
0x180027109  call    memcpy_0
0x18002710e  mov     r9d, r13d; AccessMask
0x180027111  mov     [rsi+2], r15w
0x180027116  xor     r8d, r8d; AceFlags
0x180027119  mov     [rsp+68h+pSid], r12; pSid
0x18002711e  lea     edx, [rbx+2]; dwAceRevision
0x180027121  mov     rcx, rsi; pAcl
0x180027124  call    cs:__imp_AddAccessAllowedAceEx
0x18002712a  test    eax, eax
0x18002712c  jz      short loc_18002718E
0x18002712e  xor     r9d, r9d; DaclDefaulted
0x180027131  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180027135  mov     r8, rsi; Dacl
0x180027138  mov     dl, 1; DaclPresent
0x18002713a  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180027140  test    eax, eax
0x180027142  js      short loc_18002718E
0x180027144  lea     r8, [rbp+BufferLength]; BufferLength
0x180027148  mov     [rbp+BufferLength], ebx
0x18002714b  xor     edx, edx; SelfRelativeSD
0x18002714d  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSD
0x180027151  call    cs:__imp_RtlMakeSelfRelativeSD
0x180027157  test    eax, eax
0x180027159  jns     short loc_18002718E
0x18002715b  mov     edx, [rbp+BufferLength]; uBytes
0x18002715e  lea     ecx, [rbx+40h]; uFlags
0x180027161  call    cs:__imp_LocalAlloc
0x180027167  mov     rbx, rax
0x18002716a  test    rax, rax
0x18002716d  jz      short loc_18002718E
0x18002716f  lea     r8, [rbp+BufferLength]; BufferLength
0x180027173  mov     rdx, rax; SelfRelativeSD
0x180027176  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSD
0x18002717a  call    cs:__imp_RtlMakeSelfRelativeSD
0x180027180  test    eax, eax
0x180027182  js      short loc_18002718E
0x180027184  mov     rcx, [rbp+arg_20]
0x180027188  mov     r14b, 1
0x18002718b  mov     [rcx], rbx
0x18002718e  mov     rcx, rsi; hMem
0x180027191  call    cs:__imp_LocalFree
0x180027197  test    r14b, r14b
0x18002719a  jnz     short loc_1800271AA
0x18002719c  test    rbx, rbx
0x18002719f  jz      short loc_1800271AA
0x1800271a1  mov     rcx, rbx; hMem
0x1800271a4  call    cs:__imp_LocalFree
0x1800271aa  mov     al, r14b
0x1800271ad  add     rsp, 68h
0x1800271b1  pop     r15
0x1800271b3  pop     r14
0x1800271b5  pop     r13
0x1800271b7  pop     r12
0x1800271b9  pop     rdi
0x1800271ba  pop     rsi
0x1800271bb  pop     rbx
0x1800271bc  pop     rbp
0x1800271bd  retn
```
