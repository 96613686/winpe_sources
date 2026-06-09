# VmpSetTargetCallback(VM_VOLUME_EXTENSION *,void *)

- ea: `0x1400044c0`
- end: `0x14000469d`
- name: `?VmpSetTargetCallback@@YAJPEAVVM_VOLUME_EXTENSION@@PEAX@Z`
- size: `477`
- prototype: `__int64 __fastcall(struct VM_VOLUME_EXTENSION *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1400044c0`
- `0x140005090`

## import_xrefs

- `ntoskrnl!IoAdjustStackSizeForRedirection` at `0x140004586`
- `ntoskrnl!IoAdjustStackSizeForRedirection` at `0x140004586`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000462f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000462f`

## pseudocode

```c
__int64 __fastcall VmpSetTargetCallback(struct VM_VOLUME_EXTENSION *a1, char *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rsi
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rcx
  void *v9; // rcx
  __int64 v10; // rax

  if ( *a2 )
  {
    v4 = *((_QWORD *)a2 + 12);
    if ( v4 )
    {
      v5 = 0;
      if ( *((_BYTE *)a1 + 426) )
        v5 = *((_QWORD *)a1 + 54);
      (*(void (__fastcall **)(__int64, _QWORD))(*((_QWORD *)VmRootExtension + 49) + 240LL))(v4, *((_QWORD *)a1 + 37));
      LOBYTE(v6) = *((_DWORD *)a1 + 37) > 0;
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*((_QWORD *)VmRootExtension + 49) + 232LL))(
        v5,
        *((_QWORD *)a2 + 12),
        v6);
    }
  }
  if ( !*((_BYTE *)a1 + 426) && !*a2 )
  {
    v7 = *((_QWORD *)a1 + 43);
    if ( v7 )
    {
      v8 = *((_QWORD *)a2 + 1);
      if ( v8 )
      {
        if ( v7 != v8 )
        {
          --*(_BYTE *)(*(_QWORD *)a1 + 76LL);
          IoAdjustStackSizeForRedirection(*(_QWORD *)a1, *((_QWORD *)a2 + 1), 0);
          ++*(_BYTE *)(*(_QWORD *)a1 + 76LL);
        }
      }
    }
  }
  v9 = (void *)*((_QWORD *)a1 + 47);
  *((_BYTE *)a1 + 426) = *a2;
  *((_QWORD *)a1 + 43) = *((_QWORD *)a2 + 1);
  *((_QWORD *)a1 + 45) = *((_QWORD *)a2 + 2);
  *((_QWORD *)a1 + 46) = *((_QWORD *)a2 + 3);
  *((_DWORD *)a1 + 96) = *((_DWORD *)a2 + 8);
  *((_DWORD *)a1 + 97) = *((_DWORD *)a2 + 12);
  *((_QWORD *)a1 + 49) = *((_QWORD *)a2 + 7);
  *((_QWORD *)a1 + 50) = *((_QWORD *)a2 + 8);
  *(_OWORD *)((char *)a1 + 408) = *(_OWORD *)(a2 + 72);
  *((_BYTE *)a1 + 424) = a2[88];
  *((_BYTE *)a1 + 425) = a2[89];
  *((_QWORD *)a1 + 54) = *((_QWORD *)a2 + 12);
  if ( v9 != *((void **)a2 + 5) )
  {
    if ( v9 )
      ExFreePoolWithTag(v9, 0);
    *((_QWORD *)a1 + 47) = *((_QWORD *)a2 + 5);
  }
  if ( (*(_DWORD *)(*(_QWORD *)a1 + 52LL) & 1) != 0 )
  {
    v10 = *((_QWORD *)a1 + 43);
    if ( v10 )
    {
      if ( (*(_DWORD *)(v10 + 48) & 2) != 0 )
      {
        *(_DWORD *)(*(_QWORD *)a1 + 48LL) |= 2u;
        *(_DWORD *)(*((_QWORD *)a1 + 43) + 48LL) &= ~2u;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400044c0  mov     [rsp+arg_0], rbx
0x1400044c5  mov     [rsp+arg_8], rsi
0x1400044ca  push    rdi
0x1400044cb  sub     rsp, 20h
0x1400044cf  cmp     byte ptr [rdx], 0
0x1400044d2  mov     rdi, rdx
0x1400044d5  mov     rbx, rcx
0x1400044d8  jz      short loc_140004542
0x1400044da  mov     rcx, [rdx+60h]
0x1400044de  test    rcx, rcx
0x1400044e1  jz      short loc_140004542
0x1400044e3  xor     esi, esi
0x1400044e5  cmp     [rbx+1AAh], sil
0x1400044ec  jz      short loc_1400044F5
0x1400044ee  mov     rsi, [rbx+1B0h]
0x1400044f5  mov     rax, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x1400044fc  mov     rdx, [rax+188h]
0x140004503  mov     rax, [rdx+0F0h]
0x14000450a  mov     rdx, [rbx+128h]
0x140004511  call    _guard_dispatch_icall
0x140004516  mov     rax, cs:?VmRootExtension@@3PEAVVM_ROOT_EXTENSION@@EA; VM_ROOT_EXTENSION * VmRootExtension
0x14000451d  mov     rcx, rsi
0x140004520  cmp     dword ptr [rbx+94h], 0
0x140004527  setnle  r8b
0x14000452b  mov     rdx, [rax+188h]
0x140004532  mov     rax, [rdx+0E8h]
0x140004539  mov     rdx, [rdi+60h]
0x14000453d  call    _guard_dispatch_icall
0x140004542  cmp     byte ptr [rbx+1AAh], 0
0x140004549  mov     sil, 1
0x14000454c  jnz     short loc_1400045A1
0x14000454e  cmp     byte ptr [rdi], 0
0x140004551  jnz     short loc_1400045A1
0x140004553  mov     rax, [rbx+158h]
0x14000455a  test    rax, rax
0x14000455d  jz      short loc_1400045A1
0x14000455f  mov     rcx, [rdi+8]
0x140004563  test    rcx, rcx
0x140004566  jz      short loc_1400045A1
0x140004568  cmp     rax, rcx
0x14000456b  jz      short loc_1400045A1
0x14000456d  mov     rax, [rbx]
0x140004570  xor     r8d, r8d
0x140004573  mov     cl, [rax+4Ch]
0x140004576  mov     rax, [rbx]
0x140004579  sub     cl, sil
0x14000457c  mov     [rax+4Ch], cl
0x14000457f  mov     rdx, [rdi+8]
0x140004583  mov     rcx, [rbx]
0x140004586  call    cs:__imp_IoAdjustStackSizeForRedirection
0x14000458d  nop     dword ptr [rax+rax+00h]
0x140004592  mov     rax, [rbx]
0x140004595  mov     cl, [rax+4Ch]
0x140004598  mov     rax, [rbx]
0x14000459b  add     cl, sil
0x14000459e  mov     [rax+4Ch], cl
0x1400045a1  mov     al, [rdi]
0x1400045a3  mov     rcx, [rbx+178h]; P
0x1400045aa  mov     [rbx+1AAh], al
0x1400045b0  mov     rax, [rdi+8]
0x1400045b4  mov     [rbx+158h], rax
0x1400045bb  mov     rax, [rdi+10h]
0x1400045bf  mov     [rbx+168h], rax
0x1400045c6  mov     rax, [rdi+18h]
0x1400045ca  mov     [rbx+170h], rax
0x1400045d1  mov     eax, [rdi+20h]
0x1400045d4  mov     [rbx+180h], eax
0x1400045da  mov     eax, [rdi+30h]
0x1400045dd  mov     [rbx+184h], eax
0x1400045e3  mov     rax, [rdi+38h]
0x1400045e7  mov     [rbx+188h], rax
0x1400045ee  mov     rax, [rdi+40h]
0x1400045f2  mov     [rbx+190h], rax
0x1400045f9  movups  xmm0, xmmword ptr [rdi+48h]
0x1400045fd  movdqu  xmmword ptr [rbx+198h], xmm0
0x140004605  mov     al, [rdi+58h]
0x140004608  mov     [rbx+1A8h], al
0x14000460e  mov     al, [rdi+59h]
0x140004611  mov     [rbx+1A9h], al
0x140004617  mov     rax, [rdi+60h]
0x14000461b  mov     [rbx+1B0h], rax
0x140004622  cmp     rcx, [rdi+28h]
0x140004626  jz      short loc_140004646
0x140004628  test    rcx, rcx
0x14000462b  jz      short loc_14000463B
0x14000462d  xor     edx, edx; Tag
0x14000462f  call    cs:__imp_ExFreePoolWithTag
0x140004636  nop     dword ptr [rax+rax+00h]
0x14000463b  mov     rax, [rdi+28h]
0x14000463f  mov     [rbx+178h], rax
0x140004646  mov     rax, [rbx]
0x140004649  mov     ecx, [rax+34h]
0x14000464c  test    sil, cl
0x14000464f  jz      short loc_14000468A
0x140004651  mov     rax, [rbx+158h]
0x140004658  test    rax, rax
0x14000465b  jz      short loc_14000468A
0x14000465d  mov     eax, [rax+30h]
0x140004660  test    al, 2
0x140004662  jz      short loc_14000468A
0x140004664  mov     rax, [rbx]
0x140004667  mov     ecx, [rax+30h]
0x14000466a  mov     rax, [rbx]
0x14000466d  or      ecx, 2
0x140004670  mov     [rax+30h], ecx
0x140004673  mov     rax, [rbx+158h]
0x14000467a  mov     ecx, [rax+30h]
0x14000467d  mov     rax, [rbx+158h]
0x140004684  and     ecx, 0FFFFFFFDh
0x140004687  mov     [rax+30h], ecx
0x14000468a  mov     rbx, [rsp+28h+arg_0]
0x14000468f  xor     eax, eax
0x140004691  mov     rsi, [rsp+28h+arg_8]
0x140004696  add     rsp, 20h
0x14000469a  pop     rdi
0x14000469b  retn
```
