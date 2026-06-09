# CAceList::SetExplicitAllowAce(void *,ulong,uchar)

- ea: `0x180006c70`
- end: `0x180006ddf`
- name: `?SetExplicitAllowAce@CAceList@@QEAAJPEAXKE@Z`
- size: `367`
- prototype: `__int64 __fastcall(CAceList *this, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180006180`

## callees

- `0x180002600`
- `0x18000260c`
- `0x180006c70`
- `0x1800071a8`
- `0x180007b90`
- `0x180007c50`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006d2c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180006d2c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180006cb7`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180006cb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006db2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006dbc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d79`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006db2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006dbc`

## pseudocode

```c
__int64 __fastcall CAceList::SetExplicitAllowAce(CAceList *this, void *a2)
{
  int *v2; // rax
  int v5; // esi
  int v6; // edi
  PSID *Ptr; // rax
  PSID *v8; // rbx
  unsigned int v9; // esi
  CAce *v10; // rax
  CAce *v11; // rbx
  int v12; // eax
  __int16 LengthSid; // ax
  CAce *v14; // rcx

  v2 = (int *)*((_QWORD *)this + 1);
  if ( v2 && (v5 = *v2, v6 = 0, *v2 > 0) )
  {
    while ( 1 )
    {
      Ptr = (PSID *)g_pfn_DPA_GetPtr(*((HDPA *)this + 1), v6);
      v8 = Ptr;
      if ( !*((_DWORD *)Ptr + 6) && *((_BYTE *)Ptr + 1) == 11 && EqualSid(Ptr[1], a2) )
        break;
      if ( ++v6 >= v5 )
        goto LABEL_7;
    }
    v9 = 0;
    *((_DWORD *)v8 + 1) = 65600;
  }
  else
  {
LABEL_7:
    v9 = -2147024882;
    v10 = (CAce *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v10;
    if ( v10 )
    {
      *(_QWORD *)v10 = 0x80000;
      *((_QWORD *)v10 + 1) = 0;
      *((_QWORD *)v10 + 2) = 0;
      *((_QWORD *)v10 + 3) = 0;
      if ( a2 )
      {
        LengthSid = GetLengthSid(a2);
        v12 = CAce::_Init(v11, a2, 65600, 11, 0, LengthSid + 8, 0);
      }
      else
      {
        v12 = -2147024809;
      }
      if ( v12 >= 0 )
      {
        if ( DPA_InsertPtr(*((HDPA *)this + 1), 0x7FFFFFFF, v11) != -1 )
          return 0;
        if ( !v11 )
          return v9;
        LocalFree(*((HLOCAL *)v11 + 1));
        LocalFree(*((HLOCAL *)v11 + 2));
        *((_DWORD *)v11 + 7) &= ~0x80000000;
        v14 = v11;
      }
      else
      {
        v9 = v12;
        LocalFree(*((HLOCAL *)v11 + 1));
        LocalFree(*((HLOCAL *)v11 + 2));
        v14 = v11;
        *((_DWORD *)v11 + 7) &= ~0x80000000;
      }
      operator delete(v14);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180006c70  push    rbx
0x180006c72  push    rbp
0x180006c73  push    rsi
0x180006c74  push    rdi
0x180006c75  push    r12
0x180006c77  push    r14
0x180006c79  sub     rsp, 48h
0x180006c7d  mov     rax, [rcx+8]
0x180006c81  mov     rbp, rdx
0x180006c84  mov     r14, rcx
0x180006c87  test    rax, rax
0x180006c8a  jz      short loc_180006CC7
0x180006c8c  mov     esi, [rax]
0x180006c8e  xor     edi, edi
0x180006c90  test    esi, esi
0x180006c92  jle     short loc_180006CC7
0x180006c94  mov     rcx, [r14+8]; hdpa
0x180006c98  movsxd  rdx, edi; i
0x180006c9b  call    cs:g_pfn_DPA_GetPtr
0x180006ca1  mov     rbx, rax
0x180006ca4  cmp     dword ptr [rax+18h], 0
0x180006ca8  jnz     short loc_180006CC1
0x180006caa  cmp     byte ptr [rax+1], 0Bh
0x180006cae  jnz     short loc_180006CC1
0x180006cb0  mov     rcx, [rax+8]; pSid1
0x180006cb4  mov     rdx, rbp; pSid2
0x180006cb7  call    cs:__imp_EqualSid
0x180006cbd  test    eax, eax
0x180006cbf  jnz     short loc_180006D1B
0x180006cc1  inc     edi
0x180006cc3  cmp     edi, esi
0x180006cc5  jl      short loc_180006C94
0x180006cc7  mov     r12d, 20h ; ' '
0x180006ccd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006cd4  mov     ecx, r12d; unsigned __int64
0x180006cd7  mov     esi, 8007000Eh
0x180006cdc  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006ce1  mov     rbx, rax
0x180006ce4  test    rax, rax
0x180006ce7  jz      loc_180006DD0
0x180006ced  mov     qword ptr [rax], 80000h
0x180006cf4  lea     edi, [r12-18h]
0x180006cf9  mov     qword ptr [rax+8], 0
0x180006d01  mov     qword ptr [rax+10h], 0
0x180006d09  mov     qword ptr [rax+18h], 0
0x180006d11  test    rbp, rbp
0x180006d14  jnz     short loc_180006D29
0x180006d16  lea     eax, [rsi+49h]
0x180006d19  jmp     short loc_180006D5C
0x180006d1b  xor     esi, esi
0x180006d1d  mov     dword ptr [rbx+4], 10040h
0x180006d24  jmp     loc_180006DD0
0x180006d29  mov     rcx, rbp; pSid
0x180006d2c  call    cs:__imp_GetLengthSid
0x180006d32  mov     [rsp+78h+var_48], 0; void *
0x180006d3b  mov     r9b, 0Bh; unsigned __int8
0x180006d3e  add     ax, di
0x180006d41  mov     r8d, 10040h; unsigned int
0x180006d47  mov     [rsp+78h+var_50], ax; unsigned __int16
0x180006d4c  mov     rdx, rbp; void *
0x180006d4f  mov     rcx, rbx; this
0x180006d52  mov     [rsp+78h+var_58], 0; unsigned __int8
0x180006d57  call    ?_Init@CAce@@AEAAJPEAXKEEG0@Z; CAce::_Init(void *,ulong,uchar,uchar,ushort,void *)
0x180006d5c  xor     ecx, ecx
0x180006d5e  mov     rdi, rbx
0x180006d61  test    eax, eax
0x180006d63  cmovs   rdi, rcx
0x180006d67  jns     short loc_180006D8C
0x180006d69  mov     rcx, [rbx+8]; hMem
0x180006d6d  mov     esi, eax
0x180006d6f  call    cs:__imp_LocalFree
0x180006d75  mov     rcx, [rbx+10h]; hMem
0x180006d79  call    cs:__imp_LocalFree
0x180006d7f  mov     ebp, 7FFFFFFFh
0x180006d84  mov     rcx, rbx
0x180006d87  and     [rbx+1Ch], ebp
0x180006d8a  jmp     short loc_180006DC8
0x180006d8c  mov     rcx, [r14+8]; hdpa
0x180006d90  mov     ebp, 7FFFFFFFh
0x180006d95  mov     edx, ebp; i
0x180006d97  mov     r8, rdi; p
0x180006d9a  call    cs:__imp_DPA_InsertPtr
0x180006da0  cmp     eax, 0FFFFFFFFh
0x180006da3  jz      short loc_180006DA9
0x180006da5  xor     esi, esi
0x180006da7  jmp     short loc_180006DD0
0x180006da9  test    rdi, rdi
0x180006dac  jz      short loc_180006DD0
0x180006dae  mov     rcx, [rdi+8]; hMem
0x180006db2  call    cs:__imp_LocalFree
0x180006db8  mov     rcx, [rdi+10h]; hMem
0x180006dbc  call    cs:__imp_LocalFree
0x180006dc2  and     [rdi+1Ch], ebp
0x180006dc5  mov     rcx, rdi; Block
0x180006dc8  mov     rdx, r12
0x180006dcb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006dd0  mov     eax, esi
0x180006dd2  add     rsp, 48h
0x180006dd6  pop     r14
0x180006dd8  pop     r12
0x180006dda  pop     rdi
0x180006ddb  pop     rsi
0x180006ddc  pop     rbp
0x180006ddd  pop     rbx
0x180006dde  retn
```
