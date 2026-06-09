# SqospCompleteJobsOutsideLock

- ea: `0x140002490`
- end: `0x14000253d`
- name: `SqospCompleteJobsOutsideLock`
- size: `173`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001010`
- `0x1400011c0`
- `0x140002300`

## callees

- `0x140001ab0`
- `0x140002490`

## import_xrefs

- `FLTMGR!FltCompletePendedPostOperation` at `0x14000252a`
- `FLTMGR!FltCompletePendedPostOperation` at `0x14000252a`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140002514`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140002514`

## pseudocode

```c
void __fastcall SqospCompleteJobsOutsideLock(__int64 **a1)
{
  __int64 *v1; // rdi
  __int64 *v3; // rax
  __int64 *v4; // rax
  __int64 *v5; // rdx
  __int64 *v6; // rcx
  struct _FLT_CALLBACK_DATA *v7; // rsi

  v1 = *a1;
  if ( (__int64 **)(*a1)[1] != a1 )
    goto LABEL_6;
  v3 = (__int64 *)*v1;
  if ( *(__int64 **)(*v1 + 8) != v1 )
    goto LABEL_6;
  *a1 = v3;
  v3[1] = (__int64)a1;
  if ( v1 != (__int64 *)a1 )
  {
    while ( 1 )
    {
      v4 = *a1;
      if ( (__int64 **)(*a1)[1] != a1 )
        break;
      v5 = (__int64 *)*v4;
      if ( *(__int64 **)(*v4 + 8) != v4 )
        break;
      v6 = v1 - 12;
      *a1 = v5;
      v5[1] = (__int64)a1;
      v1 = v4;
      v7 = (struct _FLT_CALLBACK_DATA *)*v6;
      if ( *((_BYTE *)v6 + 132) )
      {
        SqospDestroyJob(v6);
        FltCompletePendedPreOperation(v7, FLT_PREOP_COMPLETE, 0);
      }
      else
      {
        SqospDestroyJob(v6);
        FltCompletePendedPostOperation(v7);
      }
      if ( v1 == (__int64 *)a1 )
        return;
    }
LABEL_6:
    __fastfail(3u);
  }
}

```

## disassembly

```asm
0x140002490  mov     [rsp+arg_0], rbx
0x140002495  mov     [rsp+arg_8], rsi
0x14000249a  push    rdi
0x14000249b  sub     rsp, 20h
0x14000249f  mov     rdi, [rcx]
0x1400024a2  mov     rbx, rcx
0x1400024a5  cmp     [rdi+8], rcx
0x1400024a9  jnz     short loc_1400024E3
0x1400024ab  mov     rax, [rdi]
0x1400024ae  cmp     [rax+8], rdi
0x1400024b2  jnz     short loc_1400024E3
0x1400024b4  mov     [rcx], rax
0x1400024b7  mov     [rax+8], rcx
0x1400024bb  cmp     rdi, rcx
0x1400024be  jnz     short loc_1400024D1
0x1400024c0  mov     rbx, [rsp+28h+arg_0]
0x1400024c5  mov     rsi, [rsp+28h+arg_8]
0x1400024ca  add     rsp, 20h
0x1400024ce  pop     rdi
0x1400024cf  retn
0x1400024d1  mov     rax, [rbx]
0x1400024d4  cmp     [rax+8], rbx
0x1400024d8  jnz     short loc_1400024E3
0x1400024da  mov     rdx, [rax]
0x1400024dd  cmp     [rdx+8], rax
0x1400024e1  jz      short loc_1400024EA
0x1400024e3  mov     ecx, 3
0x1400024e8  int     29h; Win8: RtlFailFast(ecx)
0x1400024ea  lea     rcx, [rdi-60h]; Entry
0x1400024ee  mov     [rbx], rdx
0x1400024f1  mov     [rdx+8], rbx
0x1400024f5  mov     rdi, rax
0x1400024f8  cmp     byte ptr [rcx+84h], 0
0x1400024ff  mov     rsi, [rcx]
0x140002502  jz      short loc_140002522
0x140002504  call    SqospDestroyJob
0x140002509  xor     r8d, r8d; Context
0x14000250c  mov     edx, 4; CallbackStatus
0x140002511  mov     rcx, rsi; CallbackData
0x140002514  call    cs:__imp_FltCompletePendedPreOperation
0x14000251b  nop     dword ptr [rax+rax+00h]
0x140002520  jmp     short loc_140002536
0x140002522  call    SqospDestroyJob
0x140002527  mov     rcx, rsi; CallbackData
0x14000252a  call    cs:__imp_FltCompletePendedPostOperation
0x140002531  nop     dword ptr [rax+rax+00h]
0x140002536  cmp     rdi, rbx
0x140002539  jnz     short loc_1400024D1
0x14000253b  jmp     short loc_1400024C0
```
