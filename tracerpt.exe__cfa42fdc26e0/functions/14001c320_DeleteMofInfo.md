# DeleteMofInfo

- ea: `0x14001c320`
- end: `0x14001c5ce`
- name: `DeleteMofInfo`
- size: `686`
- prototype: `void __fastcall(char *lpMem, FILE *Stream)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14001db34`

## callees

- `0x14001c320`
- `0x140029f84`
- `0x140032488`
- `0x140040130`
- `0x140041010`

## import_xrefs

- `msvcrt!fwprintf` at `0x14001c386`
- `msvcrt!fwprintf` at `0x14001c3ef`
- `msvcrt!fwprintf` at `0x14001c415`
- `msvcrt!fwprintf` at `0x14001c386`
- `msvcrt!fwprintf` at `0x14001c3ef`
- `msvcrt!fwprintf` at `0x14001c415`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c438`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c487`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c502`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c54e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c576`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c596`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c438`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c487`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c502`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c54e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c576`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001c596`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c42a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c479`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c4f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c540`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c568`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c588`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c42a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c479`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c4f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c540`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c568`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001c588`

## pseudocode

```c
void __fastcall DeleteMofInfo(char *lpMem, FILE *Stream)
{
  unsigned __int16 *v4; // rax
  unsigned int i; // ebp
  void **v6; // rdi
  void ***v7; // rbx
  void **v8; // r13
  void **v9; // rax
  void **v10; // rcx
  unsigned __int8 *v11; // rax
  void **v12; // r14
  HANDLE ProcessHeap; // rax
  struct _MOF_EVENT *v14; // r14
  struct _MOF_EVENT *v15; // rax
  struct _MOF_EVENT **v16; // rdx
  struct _MOF_EVENT *v17; // rcx
  HANDLE v18; // rax
  char *v19; // rbx
  char *v20; // rax
  char **v21; // rcx
  char *v22; // rbp
  __int64 v23; // rcx
  HANDLE v24; // rax
  char *v25; // rdi
  char *v26; // rax
  char **v27; // rcx
  char *v28; // rbx
  HANDLE v29; // rax
  __int64 j; // rbx
  void *v31; // rdi
  HANDLE v32; // rax
  HANDLE v33; // rax
  __int64 v34; // [rsp+20h] [rbp-858h]
  unsigned __int16 v35[1024]; // [rsp+30h] [rbp-848h] BYREF

  if ( lpMem )
  {
    if ( Stream )
    {
      v4 = (unsigned __int16 *)*((_QWORD *)lpMem + 4);
      if ( !v4 )
        v4 = CpdiGuidToString(v35, 0x400u, (struct _GUID *)lpMem + 3);
      fwprintf(Stream, L"%s\n", v4);
    }
    for ( i = 0; i < 0x100; ++i )
    {
      v6 = (void **)&lpMem[16 * i + 64];
      v7 = (void ***)*v6;
      if ( v6 != *v6 )
      {
        do
        {
          v8 = *v7;
          if ( (*v7)[1] != v7 || (v9 = v7[1], *v9 != v7) )
LABEL_44:
            __fastfail(3u);
          *v9 = v8;
          v8[1] = v9;
          if ( Stream )
          {
            v10 = v7[2];
            if ( v10 )
            {
              if ( *((_DWORD *)v10 + 18) && (void **)((char *)v10 + *((unsigned int *)v10 + 18)) )
                fwprintf(Stream, L"   %s");
              v11 = (unsigned __int8 *)v7[2];
              LODWORD(v34) = v11[34];
              fwprintf(Stream, L"(Type:%d Level:%d Version:%d)\n", v11[37], v11[36], v34);
            }
          }
          v12 = v7[2];
          if ( v12 && *((_BYTE *)v7 + 41) )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v12);
          }
          v14 = (struct _MOF_EVENT *)v7[6];
          while ( v7 + 6 != (void ***)v14 )
          {
            v15 = *(struct _MOF_EVENT **)v14;
            if ( *(struct _MOF_EVENT **)(*(_QWORD *)v14 + 8LL) != v14 )
              goto LABEL_44;
            v16 = (struct _MOF_EVENT **)*((_QWORD *)v14 + 1);
            if ( *v16 != v14 )
              goto LABEL_44;
            v17 = v14;
            *v16 = v15;
            v14 = v15;
            *((_QWORD *)v15 + 1) = v16;
            DeleteMofEvent(v17);
          }
          v18 = GetProcessHeap();
          HeapFree(v18, 0, v7);
          v7 = (void ***)v8;
        }
        while ( v6 != v8 );
      }
    }
    v19 = (char *)*((_QWORD *)lpMem + 779);
    while ( lpMem + 6232 != v19 )
    {
      v20 = *(char **)v19;
      if ( *(char **)(*(_QWORD *)v19 + 8LL) != v19 )
        goto LABEL_44;
      v21 = (char **)*((_QWORD *)v19 + 1);
      if ( *v21 != v19 )
        goto LABEL_44;
      v22 = v19;
      *v21 = v20;
      *((_QWORD *)v20 + 1) = v21;
      v19 = v20;
      v23 = *((_QWORD *)v22 + 3);
      if ( v23 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 24LL))(v23, 1);
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v22);
    }
    v25 = (char *)*((_QWORD *)lpMem + 520);
    while ( lpMem + 4160 != v25 )
    {
      v26 = *(char **)v25;
      if ( *(char **)(*(_QWORD *)v25 + 8LL) != v25 )
        goto LABEL_44;
      v27 = (char **)*((_QWORD *)v25 + 1);
      if ( *v27 != v25 )
        goto LABEL_44;
      *v27 = v26;
      v28 = v25;
      v25 = v26;
      *((_QWORD *)v26 + 1) = v27;
      v29 = GetProcessHeap();
      HeapFree(v29, 0, v28);
    }
    for ( j = 0; j != 256; ++j )
    {
      v31 = *(void **)&lpMem[8 * j + 4184];
      if ( v31 )
      {
        v32 = GetProcessHeap();
        HeapFree(v32, 0, v31);
      }
    }
    v33 = GetProcessHeap();
    HeapFree(v33, 0, lpMem);
  }
}

```

## disassembly

```asm
0x14001c320  test    rcx, rcx
0x14001c323  jz      locret_14001C5C6
0x14001c329  mov     [rsp+arg_10], rbx
0x14001c32e  push    rbp
0x14001c32f  push    rsi
0x14001c330  push    rdi
0x14001c331  push    r12
0x14001c333  push    r13
0x14001c335  push    r14
0x14001c337  push    r15
0x14001c339  sub     rsp, 840h
0x14001c340  mov     rax, cs:__security_cookie
0x14001c347  xor     rax, rsp
0x14001c34a  mov     [rsp+878h+var_48], rax
0x14001c352  mov     r15, rdx
0x14001c355  mov     rsi, rcx
0x14001c358  test    rdx, rdx
0x14001c35b  jz      short loc_14001C38C
0x14001c35d  mov     rax, [rcx+20h]
0x14001c361  test    rax, rax
0x14001c364  jnz     short loc_14001C379
0x14001c366  lea     r8, [rcx+30h]; struct _GUID *
0x14001c36a  mov     edx, 400h; unsigned int
0x14001c36f  lea     rcx, [rsp+878h+var_848]; unsigned __int16 *
0x14001c374  call    ?CpdiGuidToString@@YAPEAGPEAGKPEAU_GUID@@@Z; CpdiGuidToString(ushort *,ulong,_GUID *)
0x14001c379  mov     r8, rax
0x14001c37c  lea     rdx, aS_2; "%s\n"
0x14001c383  mov     rcx, r15; Stream
0x14001c386  call    cs:__imp_fwprintf
0x14001c38c  xor     ebp, ebp
0x14001c38e  mov     edi, ebp
0x14001c390  add     rdi, 4
0x14001c394  shl     rdi, 4
0x14001c398  add     rdi, rsi
0x14001c39b  mov     rbx, [rdi]
0x14001c39e  cmp     rdi, rbx
0x14001c3a1  jz      loc_14001C499
0x14001c3a7  mov     r13, [rbx]
0x14001c3aa  cmp     [r13+8], rbx
0x14001c3ae  jnz     loc_14001C5C7
0x14001c3b4  mov     rax, [rbx+8]
0x14001c3b8  cmp     [rax], rbx
0x14001c3bb  jnz     loc_14001C5C7
0x14001c3c1  mov     [rax], r13
0x14001c3c4  mov     [r13+8], rax
0x14001c3c8  test    r15, r15
0x14001c3cb  jz      short loc_14001C41B
0x14001c3cd  mov     rcx, [rbx+10h]
0x14001c3d1  test    rcx, rcx
0x14001c3d4  jz      short loc_14001C41B
0x14001c3d6  cmp     dword ptr [rcx+48h], 0
0x14001c3da  jz      short loc_14001C3F5
0x14001c3dc  mov     r8d, [rcx+48h]
0x14001c3e0  add     r8, rcx
0x14001c3e3  jz      short loc_14001C3F5
0x14001c3e5  lea     rdx, aS_0; "   %s"
0x14001c3ec  mov     rcx, r15; Stream
0x14001c3ef  call    cs:__imp_fwprintf
0x14001c3f5  mov     rax, [rbx+10h]
0x14001c3f9  lea     rdx, aTypeDLevelDVer; "(Type:%d Level:%d Version:%d)\n"
0x14001c400  movzx   ecx, byte ptr [rax+22h]
0x14001c404  movzx   r9d, byte ptr [rax+24h]
0x14001c409  movzx   r8d, byte ptr [rax+25h]
0x14001c40e  mov     [rsp+878h+var_858], ecx
0x14001c412  mov     rcx, r15; Stream
0x14001c415  call    cs:__imp_fwprintf
0x14001c41b  mov     r14, [rbx+10h]
0x14001c41f  test    r14, r14
0x14001c422  jz      short loc_14001C43E
0x14001c424  cmp     byte ptr [rbx+29h], 0
0x14001c428  jz      short loc_14001C43E
0x14001c42a  call    cs:__imp_GetProcessHeap
0x14001c430  mov     r8, r14; lpMem
0x14001c433  xor     edx, edx; dwFlags
0x14001c435  mov     rcx, rax; hHeap
0x14001c438  call    cs:__imp_HeapFree
0x14001c43e  lea     r12, [rbx+30h]
0x14001c442  mov     r14, [r12]
0x14001c446  jmp     short loc_14001C474
0x14001c448  mov     rax, [r14]
0x14001c44b  cmp     [rax+8], r14
0x14001c44f  jnz     loc_14001C5C7
0x14001c455  mov     rdx, [r14+8]
0x14001c459  cmp     [rdx], r14
0x14001c45c  jnz     loc_14001C5C7
0x14001c462  mov     rcx, r14; lpMem
0x14001c465  mov     [rdx], rax
0x14001c468  mov     r14, rax
0x14001c46b  mov     [rax+8], rdx
0x14001c46f  call    ?DeleteMofEvent@@YAXPEAU_MOF_EVENT@@@Z; DeleteMofEvent(_MOF_EVENT *)
0x14001c474  cmp     r12, r14
0x14001c477  jnz     short loc_14001C448
0x14001c479  call    cs:__imp_GetProcessHeap
0x14001c47f  mov     r8, rbx; lpMem
0x14001c482  xor     edx, edx; dwFlags
0x14001c484  mov     rcx, rax; hHeap
0x14001c487  call    cs:__imp_HeapFree
0x14001c48d  mov     rbx, r13
0x14001c490  cmp     rdi, r13
0x14001c493  jnz     loc_14001C3A7
0x14001c499  inc     ebp
0x14001c49b  cmp     ebp, 100h
0x14001c4a1  jb      loc_14001C38E
0x14001c4a7  lea     rdi, [rsi+1858h]
0x14001c4ae  mov     rbx, [rdi]
0x14001c4b1  jmp     short loc_14001C508
0x14001c4b3  mov     rax, [rbx]
0x14001c4b6  cmp     [rax+8], rbx
0x14001c4ba  jnz     loc_14001C5C7
0x14001c4c0  mov     rcx, [rbx+8]
0x14001c4c4  cmp     [rcx], rbx
0x14001c4c7  jnz     loc_14001C5C7
0x14001c4cd  mov     rbp, rbx
0x14001c4d0  mov     [rcx], rax
0x14001c4d3  mov     [rax+8], rcx
0x14001c4d7  mov     rbx, rax
0x14001c4da  mov     rcx, [rbp+18h]
0x14001c4de  test    rcx, rcx
0x14001c4e1  jz      short loc_14001C4F4
0x14001c4e3  mov     rax, [rcx]
0x14001c4e6  mov     edx, 1
0x14001c4eb  mov     rax, [rax+18h]
0x14001c4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c4f4  call    cs:__imp_GetProcessHeap
0x14001c4fa  mov     r8, rbp; lpMem
0x14001c4fd  xor     edx, edx; dwFlags
0x14001c4ff  mov     rcx, rax; hHeap
0x14001c502  call    cs:__imp_HeapFree
0x14001c508  cmp     rdi, rbx
0x14001c50b  jnz     short loc_14001C4B3
0x14001c50d  lea     r14, [rsi+1040h]
0x14001c514  mov     rdi, [r14]
0x14001c517  jmp     short loc_14001C554
0x14001c519  mov     rax, [rdi]
0x14001c51c  cmp     [rax+8], rdi
0x14001c520  jnz     loc_14001C5C7
0x14001c526  mov     rcx, [rdi+8]
0x14001c52a  cmp     [rcx], rdi
0x14001c52d  jnz     loc_14001C5C7
0x14001c533  mov     [rcx], rax
0x14001c536  mov     rbx, rdi
0x14001c539  mov     rdi, rax
0x14001c53c  mov     [rax+8], rcx
0x14001c540  call    cs:__imp_GetProcessHeap
0x14001c546  mov     r8, rbx; lpMem
0x14001c549  xor     edx, edx; dwFlags
0x14001c54b  mov     rcx, rax; hHeap
0x14001c54e  call    cs:__imp_HeapFree
0x14001c554  cmp     r14, rdi
0x14001c557  jnz     short loc_14001C519
0x14001c559  xor     ebx, ebx
0x14001c55b  mov     rdi, [rsi+rbx*8+1058h]
0x14001c563  test    rdi, rdi
0x14001c566  jz      short loc_14001C57C
0x14001c568  call    cs:__imp_GetProcessHeap
0x14001c56e  mov     r8, rdi; lpMem
0x14001c571  xor     edx, edx; dwFlags
0x14001c573  mov     rcx, rax; hHeap
0x14001c576  call    cs:__imp_HeapFree
0x14001c57c  inc     rbx
0x14001c57f  cmp     rbx, 100h
0x14001c586  jnz     short loc_14001C55B
0x14001c588  call    cs:__imp_GetProcessHeap
0x14001c58e  mov     r8, rsi; lpMem
0x14001c591  xor     edx, edx; dwFlags
0x14001c593  mov     rcx, rax; hHeap
0x14001c596  call    cs:__imp_HeapFree
0x14001c59c  mov     rcx, [rsp+878h+var_48]
0x14001c5a4  xor     rcx, rsp; StackCookie
0x14001c5a7  call    __security_check_cookie
0x14001c5ac  mov     rbx, [rsp+878h+arg_10]
0x14001c5b4  add     rsp, 840h
0x14001c5bb  pop     r15
0x14001c5bd  pop     r14
0x14001c5bf  pop     r13
0x14001c5c1  pop     r12
0x14001c5c3  pop     rdi
0x14001c5c4  pop     rsi
0x14001c5c5  pop     rbp
0x14001c5c6  retn
0x14001c5c7  mov     ecx, 3
0x14001c5cc  int     29h; Win8: RtlFailFast(ecx)
```
