# PackEASLockoutData(_USER_COUNT_ENTRY *,ulong,uchar * *,ulong *)

- ea: `0x140097b4c`
- end: `0x140097c6a`
- name: `?PackEASLockoutData@@YAKPEAU_USER_COUNT_ENTRY@@KPEAPEAEPEAK@Z`
- size: `286`
- prototype: `unsigned int __fastcall(struct _USER_COUNT_ENTRY *, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140097c70`

## callees

- `0x140097b4c`
- `0x14009cc54`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140097bd0`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140097bd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140097bbf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140097bbf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140097b94`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140097c0f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140097b94`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140097c0f`

## pseudocode

```c
__int64 __fastcall PackEASLockoutData(PSID *a1, unsigned int a2, unsigned __int8 **a3, unsigned int *a4)
{
  unsigned int v4; // esi
  unsigned int v6; // ebx
  unsigned int v8; // ecx
  HANDLE ProcessHeap; // rax
  unsigned __int8 *v11; // rax
  __int64 v12; // rdi
  unsigned int v13; // ebp
  __int64 v14; // r15
  unsigned __int8 *v15; // rsi
  int v16; // ecx
  int v17; // edi
  DWORD LengthSid; // ebx
  unsigned __int8 *v19; // [rsp+20h] [rbp-48h]
  unsigned int v20; // [rsp+78h] [rbp+10h]

  v4 = 0;
  v20 = 0;
  v6 = 0;
  *a3 = 0;
  *a4 = 0;
  while ( v6 < a2 )
  {
    if ( LODWORD(a1[2 * v6]) )
    {
      v8 = v4 + GetLengthSid(a1[2 * v6 + 1]) + 4;
      if ( v8 < v4 )
        return 534;
      v4 = v8;
      v20 = v8;
    }
    ++v6;
  }
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    v11 = (unsigned __int8 *)HeapAlloc(ProcessHeap, 8u, v4);
    v19 = v11;
    if ( !v11 )
      return 14;
    v12 = 0;
    v13 = 0;
    if ( a2 )
    {
      v14 = 0;
      v15 = v11;
      do
      {
        v16 = (int)a1[2 * v14];
        if ( v16 )
        {
          *(_DWORD *)&v15[v12] = v16;
          v17 = v12 + 4;
          LengthSid = GetLengthSid(a1[2 * v14 + 1]);
          memcpy_0(&v15[v17], a1[2 * v14 + 1], LengthSid);
          v12 = LengthSid + v17;
        }
        ++v13;
        ++v14;
      }
      while ( v13 < a2 );
      v4 = v20;
      v11 = v19;
    }
    *a4 = v4;
    *a3 = v11;
  }
  return 0;
}

```

## disassembly

```asm
0x140097b4c  mov     [rsp+arg_0], rbx
0x140097b51  mov     [rsp+arg_18], r9
0x140097b56  mov     [rsp+arg_10], r8
0x140097b5b  push    rbp
0x140097b5c  push    rsi
0x140097b5d  push    rdi
0x140097b5e  push    r12
0x140097b60  push    r13
0x140097b62  push    r14
0x140097b64  push    r15
0x140097b66  sub     rsp, 30h
0x140097b6a  xor     esi, esi
0x140097b6c  mov     r13d, edx
0x140097b6f  mov     [rsp+68h+arg_8], esi
0x140097b73  xor     ebx, ebx
0x140097b75  mov     [r8], rsi
0x140097b78  mov     r12, rcx
0x140097b7b  mov     [r9], esi
0x140097b7e  cmp     ebx, r13d
0x140097b81  jnb     short loc_140097BB7
0x140097b83  mov     ecx, ebx
0x140097b85  add     rcx, rcx
0x140097b88  cmp     dword ptr [r12+rcx*8], 0
0x140097b8d  jz      short loc_140097BA9
0x140097b8f  mov     rcx, [r12+rcx*8+8]; pSid
0x140097b94  call    cs:__imp_GetLengthSid
0x140097b9a  lea     ecx, [rax+4]
0x140097b9d  add     ecx, esi
0x140097b9f  cmp     ecx, esi
0x140097ba1  jb      short loc_140097BAD
0x140097ba3  mov     esi, ecx
0x140097ba5  mov     [rsp+68h+arg_8], ecx
0x140097ba9  inc     ebx
0x140097bab  jmp     short loc_140097B7E
0x140097bad  mov     eax, 216h
0x140097bb2  jmp     loc_140097C55
0x140097bb7  test    esi, esi
0x140097bb9  jz      loc_140097C53
0x140097bbf  call    cs:__imp_GetProcessHeap
0x140097bc5  mov     r8d, esi; dwBytes
0x140097bc8  mov     edx, 8; dwFlags
0x140097bcd  mov     rcx, rax; hHeap
0x140097bd0  call    cs:__imp_HeapAlloc
0x140097bd6  mov     [rsp+68h+var_48], rax
0x140097bdb  test    rax, rax
0x140097bde  jnz     short loc_140097BE7
0x140097be0  mov     eax, 0Eh
0x140097be5  jmp     short loc_140097C55
0x140097be7  xor     edi, edi
0x140097be9  xor     ebp, ebp
0x140097beb  test    r13d, r13d
0x140097bee  jz      short loc_140097C3E
0x140097bf0  xor     r15d, r15d
0x140097bf3  mov     rsi, rax
0x140097bf6  mov     r14, r15
0x140097bf9  add     r14, r14
0x140097bfc  mov     ecx, [r12+r14*8]
0x140097c00  test    ecx, ecx
0x140097c02  jz      short loc_140097C2B
0x140097c04  mov     [rdi+rsi], ecx
0x140097c07  add     edi, 4
0x140097c0a  mov     rcx, [r12+r14*8+8]; pSid
0x140097c0f  call    cs:__imp_GetLengthSid
0x140097c15  mov     rdx, [r12+r14*8+8]; Src
0x140097c1a  mov     ecx, edi
0x140097c1c  add     rcx, rsi; void *
0x140097c1f  mov     r8d, eax; Size
0x140097c22  mov     ebx, eax
0x140097c24  call    memcpy_0
0x140097c29  add     edi, ebx
0x140097c2b  inc     ebp
0x140097c2d  inc     r15
0x140097c30  cmp     ebp, r13d
0x140097c33  jb      short loc_140097BF6
0x140097c35  mov     esi, [rsp+68h+arg_8]
0x140097c39  mov     rax, [rsp+68h+var_48]
0x140097c3e  mov     rcx, [rsp+68h+arg_18]
0x140097c46  mov     [rcx], esi
0x140097c48  mov     rcx, [rsp+68h+arg_10]
0x140097c50  mov     [rcx], rax
0x140097c53  xor     eax, eax
0x140097c55  mov     rbx, [rsp+68h+arg_0]
0x140097c5a  add     rsp, 30h
0x140097c5e  pop     r15
0x140097c60  pop     r14
0x140097c62  pop     r13
0x140097c64  pop     r12
0x140097c66  pop     rdi
0x140097c67  pop     rsi
0x140097c68  pop     rbp
0x140097c69  retn
```
