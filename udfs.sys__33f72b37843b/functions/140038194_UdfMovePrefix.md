# UdfMovePrefix

- ea: `0x140038194`
- end: `0x14003835e`
- name: `UdfMovePrefix`
- size: `458`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140034450`

## callees

- `0x1400147f8`
- `0x14002cca0`
- `0x14002ead0`
- `0x140038194`
- `0x140057f9c`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140038203`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140038203`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400382ac`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400382ac`

## pseudocode

```c
int *__fastcall UdfMovePrefix(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, __int64 a6)
{
  int v10; // ecx
  __int64 inserted; // rbx
  int v12; // r8d
  __int64 v13; // rax
  __int64 v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rdx
  int *result; // rax

  UdfRemovePrefix(a1, a2, a3 != *(_QWORD *)(a2 + 24), 0);
  UdfUpdateNamesInLcb(v10, a2, a4, a5, a6);
  inserted = UdfInsertNames(a1, *(_QWORD *)(a2 + 48), a3, a2);
  if ( a3 != *(_QWORD *)(inserted + 24) )
  {
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 16) + 1584LL));
    *(_QWORD *)(*(_QWORD *)(a1 + 16) + 1640LL) = KeGetCurrentThread();
    --*(_DWORD *)(*(_QWORD *)(inserted + 24) + 204LL);
    --*(_DWORD *)(*(_QWORD *)(inserted + 24) + 208LL);
    v13 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(inserted + 24) + 136LL) + 8LL);
    --*(_DWORD *)(v13 + 256);
    v14 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(inserted + 24) + 136LL) + 8LL);
    --*(_DWORD *)(v14 + 260);
    ++*(_DWORD *)(a3 + 204);
    ++*(_DWORD *)(a3 + 208);
    ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 136) + 8LL) + 256LL);
    ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 136) + 8LL) + 260LL);
    *(_QWORD *)(*(_QWORD *)(a1 + 16) + 1640LL) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a1 + 16) + 1584LL));
    v15 = (_QWORD *)(a3 + 536);
    v16 = *(_QWORD *)(a3 + 536);
    if ( *(_QWORD *)(v16 + 8) != a3 + 536
      || (*(_QWORD *)(inserted + 16) = v15,
          *(_QWORD *)(inserted + 8) = v16,
          *(_QWORD *)(v16 + 8) = inserted + 8,
          *v15 = inserted + 8,
          v17 = *(_QWORD *)(inserted + 48) + 160LL,
          v18 = *(_QWORD *)v17,
          *(_QWORD *)(*(_QWORD *)v17 + 8LL) != v17) )
    {
      __fastfail(3u);
    }
    *(_QWORD *)(inserted + 32) = v18;
    *(_QWORD *)(inserted + 40) = v17;
    *(_QWORD *)(v18 + 8) = inserted + 32;
    *(_QWORD *)v17 = inserted + 32;
    *(_DWORD *)(inserted + 68) &= ~0x100u;
    *(_QWORD *)(inserted + 24) = a3;
  }
  result = &WPP_GLOBAL_Control;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x8000) != 0 )
  {
    return (int *)WPP_SF_qZqq(
                    *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                    14,
                    v12,
                    a3,
                    a4,
                    inserted,
                    *(_QWORD *)(inserted + 48));
  }
  return result;
}

```

## disassembly

```asm
0x140038194  push    rbx
0x140038196  push    rbp
0x140038197  push    rsi
0x140038198  push    rdi
0x140038199  sub     rsp, 48h
0x14003819d  cmp     r8, [rdx+18h]
0x1400381a1  mov     rdi, r8
0x1400381a4  mov     rsi, r9
0x1400381a7  mov     rbx, rdx
0x1400381aa  setnz   r8b
0x1400381ae  mov     rbp, rcx
0x1400381b1  xor     r9d, r9d
0x1400381b4  call    UdfRemovePrefix
0x1400381b9  mov     rax, [rsp+68h+arg_28]
0x1400381c1  mov     r8, rsi
0x1400381c4  mov     r9, [rsp+68h+arg_20]
0x1400381cc  mov     rdx, rbx
0x1400381cf  mov     [rsp+68h+var_48], rax
0x1400381d4  call    UdfUpdateNamesInLcb
0x1400381d9  mov     rdx, [rbx+30h]
0x1400381dd  mov     r9, rbx
0x1400381e0  mov     r8, rdi
0x1400381e3  mov     rcx, rbp
0x1400381e6  call    UdfInsertNames
0x1400381eb  mov     rbx, rax
0x1400381ee  cmp     rdi, [rax+18h]
0x1400381f2  jz      loc_14003830D
0x1400381f8  mov     rcx, [rbp+10h]
0x1400381fc  add     rcx, 630h; FastMutex
0x140038203  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14003820a  nop     dword ptr [rax+rax+00h]
0x14003820f  mov     rdx, gs:188h
0x140038218  mov     rcx, [rbp+10h]
0x14003821c  mov     [rcx+668h], rdx
0x140038223  or      edx, 0FFFFFFFFh
0x140038226  mov     rax, [rbx+18h]
0x14003822a  add     [rax+0CCh], edx
0x140038230  mov     rax, [rbx+18h]
0x140038234  add     [rax+0D0h], edx
0x14003823a  mov     rax, [rbx+18h]
0x14003823e  mov     rcx, [rax+88h]
0x140038245  mov     rax, [rcx+8]
0x140038249  add     [rax+100h], edx
0x14003824f  mov     rax, [rbx+18h]
0x140038253  mov     rcx, [rax+88h]
0x14003825a  mov     rax, [rcx+8]
0x14003825e  add     [rax+104h], edx
0x140038264  inc     dword ptr [rdi+0CCh]
0x14003826a  inc     dword ptr [rdi+0D0h]
0x140038270  mov     rax, [rdi+88h]
0x140038277  mov     rcx, [rax+8]
0x14003827b  inc     dword ptr [rcx+100h]
0x140038281  mov     rax, [rdi+88h]
0x140038288  mov     rcx, [rax+8]
0x14003828c  inc     dword ptr [rcx+104h]
0x140038292  mov     rax, [rbp+10h]
0x140038296  mov     qword ptr [rax+668h], 0
0x1400382a1  mov     rcx, [rbp+10h]
0x1400382a5  add     rcx, 630h; FastMutex
0x1400382ac  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400382b3  nop     dword ptr [rax+rax+00h]
0x1400382b8  lea     rcx, [rdi+218h]
0x1400382bf  mov     rdx, [rcx]
0x1400382c2  cmp     [rdx+8], rcx
0x1400382c6  jnz     loc_140038357
0x1400382cc  lea     rax, [rbx+8]
0x1400382d0  mov     [rax+8], rcx
0x1400382d4  mov     [rax], rdx
0x1400382d7  mov     [rdx+8], rax
0x1400382db  mov     [rcx], rax
0x1400382de  mov     rcx, [rbx+30h]
0x1400382e2  add     rcx, 0A0h
0x1400382e9  mov     rdx, [rcx]
0x1400382ec  cmp     [rdx+8], rcx
0x1400382f0  jnz     short loc_140038357
0x1400382f2  lea     rax, [rbx+20h]
0x1400382f6  mov     [rax], rdx
0x1400382f9  mov     [rax+8], rcx
0x1400382fd  mov     [rdx+8], rax
0x140038301  mov     [rcx], rax
0x140038304  btr     dword ptr [rbx+44h], 8
0x140038309  mov     [rbx+18h], rdi
0x14003830d  mov     rcx, cs:WPP_GLOBAL_Control
0x140038314  lea     rax, WPP_GLOBAL_Control
0x14003831b  cmp     rcx, rax
0x14003831e  jz      short loc_14003834D
0x140038320  test    dword ptr [rcx+2Ch], 8000h
0x140038327  jz      short loc_14003834D
0x140038329  mov     rax, [rbx+30h]
0x14003832d  mov     edx, 0Eh
0x140038332  mov     rcx, [rcx+18h]
0x140038336  mov     r9, rdi
0x140038339  mov     [rsp+68h+var_38], rax
0x14003833e  mov     [rsp+68h+var_40], rbx
0x140038343  mov     [rsp+68h+var_48], rsi
0x140038348  call    WPP_SF_qZqq
0x14003834d  add     rsp, 48h
0x140038351  pop     rdi
0x140038352  pop     rsi
0x140038353  pop     rbp
0x140038354  pop     rbx
0x140038355  retn
0x140038357  mov     ecx, 3
0x14003835c  int     29h; Win8: RtlFailFast(ecx)
```
