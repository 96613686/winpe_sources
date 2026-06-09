# UdfDeleteScb

- ea: `0x140009730`
- end: `0x140009977`
- name: `UdfDeleteScb`
- size: `583`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14002e4fc`
- `0x1400312c0`
- `0x140050224`
- `0x1400537b0`

## callees

- `0x140004340`
- `0x140009730`
- `0x14000b24c`
- `0x14000c974`
- `0x140038644`
- `0x140058564`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140009781`
- `ntoskrnl!ExDeleteResourceLite` at `0x140009781`
- `ntoskrnl!KeBugCheckEx` at `0x140009819`
- `ntoskrnl!KeBugCheckEx` at `0x140009819`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400097c3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400097c3`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000994b`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14000994b`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x140009842`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x140009842`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x140009748`
- `ntoskrnl!FsRtlTeardownPerStreamContexts` at `0x140009748`
- `ntoskrnl!FsRtlFreeFileLock` at `0x140009832`
- `ntoskrnl!FsRtlFreeFileLock` at `0x140009832`

## pseudocode

```c
void __fastcall UdfDeleteScb(__int64 a1, ULONG_PTR a2)
{
  char v2; // bl
  ULONG_PTR v4; // r14
  __int64 v5; // rdi
  struct _ERESOURCE *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // eax
  FILE_LOCK *v10; // rcx
  struct _PAGED_LOOKASIDE_LIST *v11; // rcx
  bool v12; // zf

  v2 = 0;
  FsRtlTeardownPerStreamContexts((PFSRTL_ADVANCED_FCB_HEADER)a2);
  v4 = a2 + 136;
  v5 = *(_QWORD *)(*(_QWORD *)(a2 + 136) + 8LL);
  UdfUninitializeScbMcb(a2);
  UdfCleanupReservationStructures(a2);
  v6 = *(struct _ERESOURCE **)(a2 + 336);
  if ( v6 )
  {
    ExDeleteResourceLite(v6);
    UdfFreePool(a2 + 336);
  }
  v7 = *(_QWORD *)(a2 + 392);
  if ( v7 && v7 != a2 + 400 )
    UdfFreePool(a2 + 392);
  ExFreeToNPagedLookasideList(&UdfScbNonPagedLookasideList, *(PVOID *)(a2 + 424));
  v9 = *(_DWORD *)(a2 + 212);
  *(_QWORD *)(a2 + 424) = 0;
  if ( (v9 & 0x18) == 0 && *(_QWORD *)v4 )
  {
    *(_QWORD *)(*(_QWORD *)v4 + 16LL) = 0;
    UdfDeleteFcb(v8, (PVOID *)(a2 + 136));
  }
  if ( *(_WORD *)a2 == 2355 )
  {
    if ( a2 == *(_QWORD *)(v5 + 288) )
    {
      *(_QWORD *)(v5 + 288) = 0;
    }
    else
    {
      if ( a2 == *(_QWORD *)(v5 + 272) )
      {
        v12 = (*(_DWORD *)(v5 + 48) & 0x400) == 0;
        v2 = 1;
        *(_QWORD *)(v5 + 272) = 0;
        if ( !v12 )
          UdfUninitializeVmcb((void *)(v5 + 984));
        goto LABEL_39;
      }
      if ( a2 == *(_QWORD *)(v5 + 344) )
      {
        *(_QWORD *)(v5 + 344) = 0;
      }
      else if ( a2 == *(_QWORD *)(v5 + 352) )
      {
        *(_QWORD *)(v5 + 352) = 0;
      }
      else if ( a2 == *(_QWORD *)(v5 + 296) )
      {
        *(_QWORD *)(v5 + 296) = 0;
      }
      else if ( a2 == *(_QWORD *)(v5 + 312) )
      {
        *(_QWORD *)(v5 + 312) = 0;
      }
      else if ( a2 == *(_QWORD *)(v5 + 304) )
      {
        *(_QWORD *)(v5 + 304) = 0;
      }
      else if ( a2 == *(_QWORD *)(v5 + 320) )
      {
        *(_QWORD *)(v5 + 320) = 0;
      }
      else if ( a2 == *(_QWORD *)(v5 + 328) )
      {
        *(_QWORD *)(v5 + 328) = 0;
      }
      else
      {
        if ( a2 != *(_QWORD *)(v5 + 336) )
        {
LABEL_39:
          v11 = &UdfScbIndexLookasideList;
          goto LABEL_40;
        }
        *(_QWORD *)(v5 + 336) = 0;
      }
    }
    v2 = 1;
    goto LABEL_39;
  }
  if ( *(_WORD *)a2 != 2356 )
    KeBugCheckEx(0x9Bu, 0x130FCAu, a2, 0, 0);
  v10 = *(FILE_LOCK **)(a2 + 504);
  if ( v10 )
    FsRtlFreeFileLock(v10);
  FsRtlUninitializeOplock((POPLOCK)(a2 + 88));
  if ( a2 == *(_QWORD *)(v5 + 280) )
  {
    v2 = 1;
    *(_QWORD *)(v5 + 280) = 0;
  }
  v11 = &UdfScbDataLookasideList;
LABEL_40:
  ExFreeToPagedLookasideList(v11, (PVOID)a2);
  if ( v2 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v5 + 256));
    _InterlockedDecrement((volatile signed __int32 *)(v5 + 260));
  }
}

```

## disassembly

```asm
0x140009730  push    rbx
0x140009732  push    rbp
0x140009733  push    rsi
0x140009734  push    rdi
0x140009735  push    r14
0x140009737  push    r15
0x140009739  sub     rsp, 38h
0x14000973d  xor     ebp, ebp
0x14000973f  mov     rcx, rdx; AdvancedHeader
0x140009742  mov     bl, bpl
0x140009745  mov     rsi, rdx
0x140009748  call    cs:__imp_FsRtlTeardownPerStreamContexts
0x14000974f  nop     dword ptr [rax+rax+00h]
0x140009754  lea     r14, [rsi+88h]
0x14000975b  mov     rcx, rsi
0x14000975e  mov     rax, [r14]
0x140009761  mov     rdi, [rax+8]
0x140009765  call    UdfUninitializeScbMcb
0x14000976a  mov     rcx, rsi
0x14000976d  call    UdfCleanupReservationStructures
0x140009772  lea     r15, [rsi+150h]
0x140009779  mov     rcx, [r15]; Resource
0x14000977c  test    rcx, rcx
0x14000977f  jz      short loc_140009795
0x140009781  call    cs:__imp_ExDeleteResourceLite
0x140009788  nop     dword ptr [rax+rax+00h]
0x14000978d  mov     rcx, r15
0x140009790  call    UdfFreePool
0x140009795  lea     rcx, [rsi+188h]
0x14000979c  mov     rdx, [rcx]
0x14000979f  test    rdx, rdx
0x1400097a2  jz      short loc_1400097B5
0x1400097a4  lea     rax, [rsi+190h]
0x1400097ab  cmp     rdx, rax
0x1400097ae  jz      short loc_1400097B5
0x1400097b0  call    UdfFreePool
0x1400097b5  mov     rdx, [rsi+1A8h]; Entry
0x1400097bc  lea     rcx, UdfScbNonPagedLookasideList; Lookaside
0x1400097c3  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400097ca  nop     dword ptr [rax+rax+00h]
0x1400097cf  mov     eax, [rsi+0D4h]
0x1400097d5  mov     [rsi+1A8h], rbp
0x1400097dc  test    al, 18h
0x1400097de  jnz     short loc_1400097F4
0x1400097e0  mov     rax, [r14]
0x1400097e3  test    rax, rax
0x1400097e6  jz      short loc_1400097F4
0x1400097e8  mov     rdx, r14
0x1400097eb  mov     [rax+10h], rbp
0x1400097ef  call    UdfDeleteFcb
0x1400097f4  movsx   ecx, word ptr [rsi]
0x1400097f7  sub     ecx, 933h
0x1400097fd  jz      short loc_14000986C
0x1400097ff  cmp     ecx, 1
0x140009802  jz      short loc_140009826
0x140009804  xor     r9d, r9d; BugCheckParameter3
0x140009807  mov     [rsp+68h+BugCheckParameter4], rbp; BugCheckParameter4
0x14000980c  mov     r8, rsi; BugCheckParameter2
0x14000980f  mov     edx, 130FCAh; BugCheckParameter1
0x140009814  mov     ecx, 9Bh; BugCheckCode
0x140009819  call    cs:__imp_KeBugCheckEx
0x140009826  mov     rcx, [rsi+1F8h]; FileLock
0x14000982d  test    rcx, rcx
0x140009830  jz      short loc_14000983E
0x140009832  call    cs:__imp_FsRtlFreeFileLock
0x140009839  nop     dword ptr [rax+rax+00h]
0x14000983e  lea     rcx, [rsi+58h]; Oplock
0x140009842  call    cs:__imp_FsRtlUninitializeOplock
0x140009849  nop     dword ptr [rax+rax+00h]
0x14000984e  cmp     rsi, [rdi+118h]
0x140009855  jnz     short loc_140009860
0x140009857  mov     bl, 1
0x140009859  mov     [rdi+118h], rbp
0x140009860  lea     rcx, UdfScbDataLookasideList
0x140009867  jmp     loc_140009948
0x14000986c  cmp     rsi, [rdi+120h]
0x140009873  jnz     short loc_140009881
0x140009875  mov     [rdi+120h], rbp
0x14000987c  jmp     loc_14000993F
0x140009881  cmp     rsi, [rdi+110h]
0x140009888  jnz     short loc_1400098B1
0x14000988a  test    dword ptr [rdi+30h], 400h
0x140009891  mov     bl, 1
0x140009893  mov     [rdi+110h], rbp
0x14000989a  jz      loc_140009941
0x1400098a0  lea     rcx, [rdi+3D8h]; void *
0x1400098a7  call    UdfUninitializeVmcb
0x1400098ac  jmp     loc_140009941
0x1400098b1  cmp     rsi, [rdi+158h]
0x1400098b8  jnz     short loc_1400098C3
0x1400098ba  mov     [rdi+158h], rbp
0x1400098c1  jmp     short loc_14000993F
0x1400098c3  cmp     rsi, [rdi+160h]
0x1400098ca  jnz     short loc_1400098D5
0x1400098cc  mov     [rdi+160h], rbp
0x1400098d3  jmp     short loc_14000993F
0x1400098d5  cmp     rsi, [rdi+128h]
0x1400098dc  jnz     short loc_1400098E7
0x1400098de  mov     [rdi+128h], rbp
0x1400098e5  jmp     short loc_14000993F
0x1400098e7  cmp     rsi, [rdi+138h]
0x1400098ee  jnz     short loc_1400098F9
0x1400098f0  mov     [rdi+138h], rbp
0x1400098f7  jmp     short loc_14000993F
0x1400098f9  cmp     rsi, [rdi+130h]
0x140009900  jnz     short loc_14000990B
0x140009902  mov     [rdi+130h], rbp
0x140009909  jmp     short loc_14000993F
0x14000990b  cmp     rsi, [rdi+140h]
0x140009912  jnz     short loc_14000991D
0x140009914  mov     [rdi+140h], rbp
0x14000991b  jmp     short loc_14000993F
0x14000991d  cmp     rsi, [rdi+148h]
0x140009924  jnz     short loc_14000992F
0x140009926  mov     [rdi+148h], rbp
0x14000992d  jmp     short loc_14000993F
0x14000992f  cmp     rsi, [rdi+150h]
0x140009936  jnz     short loc_140009941
0x140009938  mov     [rdi+150h], rbp
0x14000993f  mov     bl, 1
0x140009941  lea     rcx, UdfScbIndexLookasideList; Lookaside
0x140009948  mov     rdx, rsi; Entry
0x14000994b  call    cs:__imp_ExFreeToPagedLookasideList
0x140009952  nop     dword ptr [rax+rax+00h]
0x140009957  test    bl, bl
0x140009959  jz      short loc_140009969
0x14000995b  lock dec dword ptr [rdi+100h]
0x140009962  lock dec dword ptr [rdi+104h]
0x140009969  add     rsp, 38h
0x14000996d  pop     r15
0x14000996f  pop     r14
0x140009971  pop     rdi
0x140009972  pop     rsi
0x140009973  pop     rbp
0x140009974  pop     rbx
0x140009975  retn
```
