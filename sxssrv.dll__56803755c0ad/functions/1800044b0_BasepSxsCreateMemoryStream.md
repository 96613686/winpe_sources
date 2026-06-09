# BasepSxsCreateMemoryStream

- ea: `0x1800044b0`
- end: `0x180004748`
- name: `BasepSxsCreateMemoryStream`
- size: `664`
- prototype: `__int64 __fastcall(__int64 SourceProcessHandle, __int64, _QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180003170`

## callees

- `0x1800044b0`
- `0x180004750`
- `0x180006580`
- `0x180006598`
- `0x180007010`

## import_xrefs

- `ntdll!NtDuplicateObject` at `0x18000451d`
- `ntdll!NtDuplicateObject` at `0x18000463a`
- `ntdll!NtDuplicateObject` at `0x18000451d`
- `ntdll!NtDuplicateObject` at `0x18000463a`

## pseudocode

```c
__int64 __fastcall BasepSxsCreateMemoryStream(
        __int64 SourceProcessHandle,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v7; // rbp
  char v8; // al
  HANDLE v9; // rdx
  NTSTATUS v10; // esi
  void *v11; // rdx
  int v12; // ecx
  __int64 (__fastcall **v13)(); // r9
  void *v14; // rax
  __int64 v15; // rcx
  char *v16; // rax
  __int64 v17; // r8
  __int64 v19; // rcx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  char *v23; // rdx
  HANDLE v24; // rax
  __int64 v25; // rcx
  PVOID BaseAddress; // [rsp+40h] [rbp-28h] BYREF
  HANDLE Handle; // [rsp+78h] [rbp+10h] BYREF
  void *TargetHandle; // [rsp+88h] [rbp+20h] BYREF

  TargetHandle = 0;
  Handle = 0;
  v7 = SourceProcessHandle;
  BaseAddress = 0;
  v8 = *(_BYTE *)(a2 + 2);
  if ( v8 == 2 )
  {
    v9 = (HANDLE)SourceProcessHandle;
    goto LABEL_3;
  }
  v9 = *(HANDLE *)(a2 + 32);
  if ( (unsigned __int8)(v8 - 4) <= 1u )
LABEL_3:
    SourceProcessHandle = -1;
  v10 = NtDuplicateObject((HANDLE)SourceProcessHandle, v9, (HANDLE)0xFFFFFFFFFFFFFFFFLL, &TargetHandle, 0, 0, 2u);
  if ( v10 < 0 )
  {
    TargetHandle = 0;
    goto LABEL_10;
  }
  v11 = *(void **)(a2 + 24);
  if ( !v11
    || ((unsigned __int8)(*(_BYTE *)(a2 + 2) - 4) <= 1u ? (v19 = -1) : (v19 = v7),
        v10 = NtDuplicateObject((HANDLE)v19, v11, (HANDLE)0xFFFFFFFFFFFFFFFFLL, &Handle, 0, 0, 2u),
        v10 >= 0) )
  {
    v12 = *(unsigned __int8 *)(a2 + 2);
    if ( v12 != 1 )
    {
      v20 = v12 - 2;
      if ( v20 )
      {
        v21 = v20 - 1;
        if ( !v21 )
        {
LABEL_28:
          v10 = BasepSxsMapViewOfSection(&BaseAddress, *(_QWORD *)(a2 + 48));
          if ( v10 < 0 )
            goto LABEL_10;
          a3[1] = 0;
          a3[4] = 0;
          v13 = off_180008070;
          a3[6] = 0;
          v23 = (char *)BaseAddress;
          *a3 = off_180008070;
          a3[5] = BaseSxsFinalReleaseMemoryMappedStream;
          v24 = Handle;
          a3[7] = 0;
          a3[3] = v23;
          a3[2] = v23;
          v25 = *(_QWORD *)(a2 + 48);
          a3[7] = v24;
          BaseAddress = 0;
          Handle = 0;
          v16 = &v23[v25];
          goto LABEL_8;
        }
        v22 = v21 - 1;
        if ( v22 )
        {
          if ( v22 != 1 )
          {
            v10 = -1073741811;
            goto LABEL_10;
          }
          goto LABEL_28;
        }
      }
    }
    a3[1] = 0;
    a3[2] = 0;
    v13 = off_180008000;
    a3[3] = 0;
    a3[4] = 0;
    a3[5] = RtlFinalReleaseOutOfProcessMemoryStream;
    v14 = TargetHandle;
    *a3 = off_180008000;
    a3[6] = v14;
    v15 = *(_QWORD *)(a2 + 40);
    a3[3] = v15;
    a3[2] = v15;
    v16 = (char *)(v15 + *(_QWORD *)(a2 + 48));
    TargetHandle = 0;
LABEL_8:
    v17 = a5;
    a3[4] = v16;
    v10 = 0;
    if ( ((int (__fastcall *)(_QWORD *, GUID *, __int64))*v13)(a3, &IID_ISequentialStream, v17) < 0 )
      v10 = -1073741637;
  }
LABEL_10:
  if ( Handle )
    NtClose_0(Handle);
  if ( TargetHandle )
    NtClose_0(TargetHandle);
  if ( BaseAddress )
    NtUnmapViewOfSection_0((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800044b0  mov     rax, rsp
0x1800044b3  mov     [rax+8], rbx
0x1800044b7  mov     [rax+18h], rbp
0x1800044bb  mov     [rax+20h], r9
0x1800044bf  push    rsi
0x1800044c0  push    rdi
0x1800044c1  push    r14
0x1800044c3  sub     rsp, 50h
0x1800044c7  xor     r14d, r14d
0x1800044ca  mov     rbx, r8
0x1800044cd  mov     [rax+20h], r14
0x1800044d1  mov     rdi, rdx
0x1800044d4  mov     [rax+10h], r14
0x1800044d8  mov     rbp, rcx
0x1800044db  mov     [rax-28h], r14
0x1800044df  movzx   eax, byte ptr [rdx+2]
0x1800044e3  cmp     al, 2
0x1800044e5  jz      loc_180004655
0x1800044eb  mov     rdx, [rdx+20h]; SourceHandle
0x1800044ef  sub     al, 4
0x1800044f1  cmp     al, 1
0x1800044f3  ja      loc_18000465D
0x1800044f9  mov     r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x180004500  mov     rcx, r8; SourceProcessHandle
0x180004503  mov     [rsp+68h+Options], 2; Options
0x18000450b  lea     r9, [rsp+68h+TargetHandle]; TargetHandle
0x180004513  mov     [rsp+68h+HandleAttributes], r14d; HandleAttributes
0x180004518  mov     [rsp+68h+DesiredAccess], r14d; DesiredAccess
0x18000451d  call    cs:__imp_NtDuplicateObject
0x180004524  nop     dword ptr [rax+rax+00h]
0x180004529  mov     esi, eax
0x18000452b  test    eax, eax
0x18000452d  js      loc_180004711
0x180004533  mov     rdx, [rdi+18h]; SourceHandle
0x180004537  test    rdx, rdx
0x18000453a  jnz     loc_18000460B
0x180004540  movzx   ecx, byte ptr [rdi+2]
0x180004544  cmp     ecx, 1
0x180004547  jnz     loc_180004669
0x18000454d  mov     [rbx+8], r14
0x180004551  lea     rax, RtlFinalReleaseOutOfProcessMemoryStream
0x180004558  mov     [rbx+10h], r14
0x18000455c  lea     r9, off_180008000
0x180004563  mov     [rbx+18h], r14
0x180004567  mov     [rbx+20h], r14
0x18000456b  mov     [rbx+28h], rax
0x18000456f  mov     rax, [rsp+68h+TargetHandle]
0x180004577  mov     [rbx], r9
0x18000457a  mov     [rbx+30h], rax
0x18000457e  mov     rcx, [rdi+28h]
0x180004582  mov     [rbx+18h], rcx
0x180004586  mov     [rbx+10h], rcx
0x18000458a  mov     rax, [rdi+30h]
0x18000458e  add     rax, rcx
0x180004591  mov     [rsp+68h+TargetHandle], r14
0x180004599  mov     r8, [rsp+68h+arg_20]
0x1800045a1  lea     rdx, IID_ISequentialStream
0x1800045a8  mov     [rbx+20h], rax
0x1800045ac  mov     rcx, rbx
0x1800045af  mov     rax, [r9]
0x1800045b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045b7  test    eax, eax
0x1800045b9  mov     esi, r14d
0x1800045bc  mov     ecx, 0C00000BBh
0x1800045c1  cmovs   esi, ecx
0x1800045c4  mov     rcx, [rsp+68h+Handle]; Handle
0x1800045c9  test    rcx, rcx
0x1800045cc  jz      short loc_1800045D3
0x1800045ce  call    NtClose_0
0x1800045d3  mov     rcx, [rsp+68h+TargetHandle]; Handle
0x1800045db  test    rcx, rcx
0x1800045de  jnz     loc_18000472D
0x1800045e4  mov     rdx, [rsp+68h+BaseAddress]; BaseAddress
0x1800045e9  test    rdx, rdx
0x1800045ec  jnz     loc_180004737
0x1800045f2  mov     rbx, [rsp+68h+arg_0]
0x1800045f7  mov     eax, esi
0x1800045f9  mov     rbp, [rsp+68h+arg_10]
0x180004601  add     rsp, 50h
0x180004605  pop     r14
0x180004607  pop     rdi
0x180004608  pop     rsi
0x180004609  retn
0x18000460b  movzx   eax, byte ptr [rdi+2]
0x18000460f  lea     r9, [rsp+68h+Handle]; TargetHandle
0x180004614  mov     [rsp+68h+Options], 2; Options
0x18000461c  sub     al, 4
0x18000461e  mov     [rsp+68h+HandleAttributes], r14d; HandleAttributes
0x180004623  mov     [rsp+68h+DesiredAccess], r14d; DesiredAccess
0x180004628  cmp     al, 1
0x18000462a  jbe     loc_18000471E
0x180004630  mov     r8, 0FFFFFFFFFFFFFFFFh; TargetProcessHandle
0x180004637  mov     rcx, rbp; SourceProcessHandle
0x18000463a  call    cs:__imp_NtDuplicateObject
0x180004641  nop     dword ptr [rax+rax+00h]
0x180004646  mov     esi, eax
0x180004648  test    eax, eax
0x18000464a  jns     loc_180004540
0x180004650  jmp     loc_1800045C4
0x180004655  mov     rdx, rbp
0x180004658  jmp     loc_1800044F9
0x18000465d  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180004664  jmp     loc_180004503
0x180004669  sub     ecx, 2
0x18000466c  jz      loc_18000454D
0x180004672  sub     ecx, 1
0x180004675  jz      short loc_18000468F
0x180004677  sub     ecx, 1
0x18000467a  jz      loc_18000454D
0x180004680  cmp     ecx, 1
0x180004683  jz      short loc_18000468F
0x180004685  mov     esi, 0C000000Dh
0x18000468a  jmp     loc_1800045C4
0x18000468f  mov     rax, [rdi+30h]
0x180004693  lea     rcx, [rsp+68h+BaseAddress]; BaseAddress
0x180004698  mov     r9, [rdi+28h]
0x18000469c  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x1800046a3  mov     r8, [rsp+68h+TargetHandle]
0x1800046ab  mov     qword ptr [rsp+68h+DesiredAccess], rax; ULONG_PTR
0x1800046b0  call    BasepSxsMapViewOfSection
0x1800046b5  mov     esi, eax
0x1800046b7  test    eax, eax
0x1800046b9  js      loc_1800045C4
0x1800046bf  mov     [rbx+8], r14
0x1800046c3  lea     rax, BaseSxsFinalReleaseMemoryMappedStream
0x1800046ca  mov     [rbx+20h], r14
0x1800046ce  lea     r9, off_180008070
0x1800046d5  mov     [rbx+30h], r14
0x1800046d9  mov     rdx, [rsp+68h+BaseAddress]
0x1800046de  mov     [rbx], r9
0x1800046e1  mov     [rbx+28h], rax
0x1800046e5  mov     rax, [rsp+68h+Handle]
0x1800046ea  mov     [rbx+38h], r14
0x1800046ee  mov     [rbx+18h], rdx
0x1800046f2  mov     [rbx+10h], rdx
0x1800046f6  mov     rcx, [rdi+30h]
0x1800046fa  mov     [rbx+38h], rax
0x1800046fe  mov     [rsp+68h+BaseAddress], r14
0x180004703  mov     [rsp+68h+Handle], r14
0x180004708  lea     rax, [rcx+rdx]
0x18000470c  jmp     loc_180004599
0x180004711  mov     [rsp+68h+TargetHandle], r14
0x180004719  jmp     loc_1800045C4
0x18000471e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180004725  mov     r8, rcx
0x180004728  jmp     loc_18000463A
0x18000472d  call    NtClose_0
0x180004732  jmp     loc_1800045E4
0x180004737  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18000473e  call    NtUnmapViewOfSection_0
0x180004743  jmp     loc_1800045F2
```
