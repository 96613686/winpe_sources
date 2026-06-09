# RaFreeRaidResources

- ea: `0x14001c970`
- end: `0x14001cae0`
- name: `RaFreeRaidResources`
- size: `368`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x14001c2c0`
- `0x1400873c0`
- `0x14018e72c`

## callees

- `0x140008210`
- `0x14000ebfc`
- `0x14001c970`
- `0x14014b440`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001c9d3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14014de43`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14014de81`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14001c9d3`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14014de43`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14014de81`
- `ntoskrnl!IoFreeWorkItem` at `0x14001caa8`
- `ntoskrnl!IoFreeWorkItem` at `0x14001cac4`
- `ntoskrnl!IoFreeWorkItem` at `0x14001caa8`
- `ntoskrnl!IoFreeWorkItem` at `0x14001cac4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c9f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014de6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014deaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014deca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001c9f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014de6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014deaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14014deca`
- `ntoskrnl!MmFreeContiguousMemory` at `0x14001ca58`
- `ntoskrnl!MmFreeContiguousMemory` at `0x14001ca58`

## pseudocode

```c
void __fastcall RaFreeRaidResources(__int64 a1, __int64 a2, char a3)
{
  __int64 v5; // rdi
  __int64 v6; // r14
  __int64 v7; // rbx
  PSLIST_ENTRY v8; // rax
  int v9; // eax
  struct _IO_WORKITEM *v10; // rcx
  struct _IO_WORKITEM *v11; // rcx
  __int64 v12; // r10
  __int64 v13; // rbx
  PSLIST_ENTRY i; // rax
  int v15; // [rsp+20h] [rbp-28h]

  if ( a1 )
  {
    if ( a2 )
    {
      v5 = a1 + 64;
      if ( a1 != -64 )
      {
        v6 = *(_QWORD *)(a2 + 64);
        if ( *(_DWORD *)v6 == 1431193940 )
          v6 = *(_QWORD *)(v6 + 24);
        v7 = 0;
        if ( *(_DWORD *)(a1 + 128) )
        {
          do
          {
            for ( i = ExpInterlockedPopEntrySList(*(PSLIST_HEADER *)(*(_QWORD *)v5 + 8 * v7));
                  i;
                  i = ExpInterlockedPopEntrySList(*(PSLIST_HEADER *)(*(_QWORD *)v5 + 8 * v7)) )
            {
              if ( a3 )
                StorFreeContiguousIoResources(v6, i);
              else
                ExFreePoolWithTag(i, 0x53526152u);
            }
            v7 = (unsigned int)(v7 + 1);
          }
          while ( (unsigned int)v7 < *(_DWORD *)(v5 + 64) );
        }
        else if ( *(_DWORD *)(a1 + 136) )
        {
          do
          {
            v8 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v5);
            if ( !v8 )
              break;
            if ( a3 )
            {
              if ( (unsigned __int8)IsDmarEnabled(v6) )
              {
                LOBYTE(v15) = 1;
                (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int))(*(_QWORD *)(*(_QWORD *)(v6 + 880) + 8LL)
                                                                             + 24LL))(
                  *(_QWORD *)(v6 + 880),
                  *(unsigned int *)(v12 + 16),
                  *(_QWORD *)(v12 + 24),
                  v12,
                  v15);
              }
              else
              {
                MmFreeContiguousMemory((PVOID)v12);
              }
            }
            else
            {
              ExFreePoolWithTag(v8, 0x53526152u);
            }
            LODWORD(v7) = v7 + 1;
          }
          while ( (unsigned int)v7 < *(_DWORD *)(v5 + 72) );
        }
        v9 = *(_DWORD *)(v5 + 64);
        *(_DWORD *)(v5 + 72) = 0;
        if ( v9 )
        {
          v13 = 0;
          do
          {
            ExFreePoolWithTag(*(PVOID *)(*(_QWORD *)v5 + 8 * v13), 0x53526152u);
            v13 = (unsigned int)(v13 + 1);
          }
          while ( (unsigned int)v13 < *(_DWORD *)(v5 + 64) );
          ExFreePoolWithTag(*(PVOID *)v5, 0x53526152u);
          *(_DWORD *)(v5 + 64) = 0;
        }
        v10 = *(struct _IO_WORKITEM **)(a1 + 288);
        if ( v10 )
        {
          IoFreeWorkItem(v10);
          *(_QWORD *)(a1 + 288) = 0;
        }
        v11 = *(struct _IO_WORKITEM **)(a1 + 312);
        if ( v11 )
        {
          IoFreeWorkItem(v11);
          *(_QWORD *)(a1 + 312) = 0;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14001c970  test    rcx, rcx
0x14001c973  jnz     short loc_14001C977
0x14001c975  retn
0x14001c977  push    rsi
0x14001c978  push    r15
0x14001c97a  sub     rsp, 38h
0x14001c97e  movzx   esi, r8b
0x14001c982  mov     r15, rcx
0x14001c985  test    rdx, rdx
0x14001c988  jz      loc_14001CA40
0x14001c98e  mov     [rsp+48h+arg_10], rdi
0x14001c993  lea     rdi, [rcx+40h]
0x14001c997  test    rdi, rdi
0x14001c99a  jz      loc_14001CA3B
0x14001c9a0  mov     [rsp+48h+var_18], r14
0x14001c9a5  mov     r14, [rdx+40h]
0x14001c9a9  cmp     dword ptr [r14], 554E4954h
0x14001c9b0  jnz     short loc_14001C9B6
0x14001c9b2  mov     r14, [r14+18h]
0x14001c9b6  mov     eax, [rdi+40h]
0x14001c9b9  mov     [rsp+48h+arg_0], rbx
0x14001c9be  xor     ebx, ebx
0x14001c9c0  test    eax, eax
0x14001c9c2  jnz     loc_14001CA8F
0x14001c9c8  cmp     [rdi+48h], ebx
0x14001c9cb  jbe     short loc_14001CA07
0x14001c9cd  nop     dword ptr [rax]
0x14001c9d0  mov     rcx, rdi; ListHead
0x14001c9d3  call    cs:__imp_ExpInterlockedPopEntrySList
0x14001c9da  nop     dword ptr [rax+rax+00h]
0x14001c9df  mov     r10, rax
0x14001c9e2  test    rax, rax
0x14001c9e5  jz      short loc_14001CA07
0x14001c9e7  test    sil, sil
0x14001c9ea  jnz     short loc_14001CA49
0x14001c9ec  mov     edx, 53526152h; Tag
0x14001c9f1  mov     rcx, rax; P
0x14001c9f4  call    cs:__imp_ExFreePoolWithTag
0x14001c9fb  nop     dword ptr [rax+rax+00h]
0x14001ca00  inc     ebx
0x14001ca02  cmp     ebx, [rdi+48h]
0x14001ca05  jb      short loc_14001C9D0
0x14001ca07  mov     eax, [rdi+40h]
0x14001ca0a  mov     r14, [rsp+48h+var_18]
0x14001ca0f  mov     dword ptr [rdi+48h], 0
0x14001ca16  test    eax, eax
0x14001ca18  jnz     short loc_14001CA99
0x14001ca1a  mov     rcx, [r15+120h]; IoWorkItem
0x14001ca21  mov     rbx, [rsp+48h+arg_0]
0x14001ca26  test    rcx, rcx
0x14001ca29  jnz     short loc_14001CAA8
0x14001ca2b  mov     rcx, [r15+138h]; IoWorkItem
0x14001ca32  test    rcx, rcx
0x14001ca35  jnz     loc_14001CAC4
0x14001ca3b  mov     rdi, [rsp+48h+arg_10]
0x14001ca40  add     rsp, 38h
0x14001ca44  pop     r15
0x14001ca46  pop     rsi
0x14001ca47  retn
0x14001ca49  mov     rcx, r14
0x14001ca4c  call    IsDmarEnabled
0x14001ca51  test    al, al
0x14001ca53  jnz     short loc_14001CA66
0x14001ca55  mov     rcx, r10; BaseAddress
0x14001ca58  call    cs:__imp_MmFreeContiguousMemory
0x14001ca5f  nop     dword ptr [rax+rax+00h]
0x14001ca64  jmp     short loc_14001CA00
0x14001ca66  mov     rcx, [r14+370h]
0x14001ca6d  mov     r9, r10
0x14001ca70  mov     r8, [r10+18h]
0x14001ca74  mov     byte ptr [rsp+48h+var_28], 1
0x14001ca79  mov     rdx, [rcx+8]
0x14001ca7d  mov     rax, [rdx+18h]
0x14001ca81  mov     edx, [r10+10h]
0x14001ca85  call    _guard_dispatch_icall
0x14001ca8a  jmp     loc_14001CA00
0x14001ca8f  mov     [rsp+48h+arg_8], rbp
0x14001ca94  jmp     loc_14014DE34
0x14001ca99  xor     ebx, ebx
0x14001ca9b  test    eax, eax
0x14001ca9d  jnz     loc_14014DEA3
0x14001caa3  jmp     loc_14014DEC2
0x14001caa8  call    cs:__imp_IoFreeWorkItem
0x14001caaf  nop     dword ptr [rax+rax+00h]
0x14001cab4  mov     qword ptr [r15+120h], 0
0x14001cabf  jmp     loc_14001CA2B
0x14001cac4  call    cs:__imp_IoFreeWorkItem
0x14001cacb  nop     dword ptr [rax+rax+00h]
0x14001cad0  mov     qword ptr [r15+138h], 0
0x14001cadb  jmp     loc_14001CA3B
0x14014de34  mov     rcx, [rdi]
0x14014de37  lea     rbp, ds:0[rbx*8]
0x14014de3f  mov     rcx, [rcx+rbp]; ListHead
0x14014de43  call    cs:__imp_ExpInterlockedPopEntrySList
0x14014de4a  nop     dword ptr [rax+rax+00h]
0x14014de4f  test    rax, rax
0x14014de52  jz      short loc_14014DE92
0x14014de54  test    sil, sil
0x14014de57  jz      short loc_14014DE66
0x14014de59  mov     rdx, rax
0x14014de5c  mov     rcx, r14
0x14014de5f  call    StorFreeContiguousIoResources
0x14014de64  jmp     short loc_14014DE7A
0x14014de66  mov     edx, 53526152h; Tag
0x14014de6b  mov     rcx, rax; P
0x14014de6e  call    cs:__imp_ExFreePoolWithTag
0x14014de75  nop     dword ptr [rax+rax+00h]
0x14014de7a  mov     rcx, [rdi]
0x14014de7d  mov     rcx, [rcx+rbp]; ListHead
0x14014de81  call    cs:__imp_ExpInterlockedPopEntrySList
0x14014de88  nop     dword ptr [rax+rax+00h]
0x14014de8d  test    rax, rax
0x14014de90  jnz     short loc_14014DE54
0x14014de92  inc     ebx
0x14014de94  cmp     ebx, [rdi+40h]
0x14014de97  jb      short loc_14014DE34
0x14014de99  mov     rbp, [rsp+48h+arg_8]
0x14014de9e  jmp     loc_14001CA07
0x14014dea3  mov     rcx, [rdi]
0x14014dea6  mov     edx, 53526152h; Tag
0x14014deab  mov     rcx, [rcx+rbx*8]; P
0x14014deaf  call    cs:__imp_ExFreePoolWithTag
0x14014deb6  nop     dword ptr [rax+rax+00h]
0x14014debb  inc     ebx
0x14014debd  cmp     ebx, [rdi+40h]
0x14014dec0  jb      short loc_14014DEA3
0x14014dec2  mov     rcx, [rdi]; P
0x14014dec5  mov     edx, 53526152h; Tag
0x14014deca  call    cs:__imp_ExFreePoolWithTag
0x14014ded1  nop     dword ptr [rax+rax+00h]
0x14014ded6  mov     dword ptr [rdi+40h], 0
0x14014dedd  jmp     loc_14001CA1A
```
