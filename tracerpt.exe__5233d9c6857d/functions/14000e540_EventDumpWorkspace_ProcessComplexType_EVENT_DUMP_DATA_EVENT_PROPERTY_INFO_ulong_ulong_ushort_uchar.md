# EventDumpWorkspace::ProcessComplexType(_EVENT_DUMP_DATA *,_EVENT_PROPERTY_INFO *,ulong,ulong *,ushort &,uchar)

- ea: `0x14000e540`
- end: `0x14000e7a1`
- name: `?ProcessComplexType@EventDumpWorkspace@@IEAAKPEAU_EVENT_DUMP_DATA@@PEAU_EVENT_PROPERTY_INFO@@KPEAKAEAGE@Z`
- size: `609`
- prototype: `unsigned int __fastcall(EventDumpWorkspace *__hidden this, struct _EVENT_DUMP_DATA *, struct _EVENT_PROPERTY_INFO *, unsigned int, unsigned int *, unsigned __int16 *, unsigned __int8)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000e254`
- `0x14000e540`

## callees

- `0x14000d9e0`
- `0x14000e540`
- `0x14000e7a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e5fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e5fe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000e61d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000e61d`

## pseudocode

```c
unsigned int __fastcall EventDumpWorkspace::ProcessComplexType(
        EventDumpWorkspace *this,
        struct _EVENT_DUMP_DATA *a2,
        struct _EVENT_PROPERTY_INFO *a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned __int16 *a6,
        unsigned __int8 a7)
{
  __int64 count; // rdi
  __int64 v10; // r12
  char *v12; // rsi
  __int64 v13; // rax
  int OutType; // ebp
  __int64 v15; // rbp
  HANDLE ProcessHeap; // rax
  LPVOID v17; // rax
  unsigned int result; // eax
  unsigned __int16 v19; // bp
  int v20; // r10d
  unsigned __int16 v21; // r13
  __int64 v22; // r9
  struct _EVENT_PROPERTY_INFO *v23; // r8
  struct _EVENT_DUMP_DATA *v24; // rdx
  __int64 v25; // r9
  __int64 v26; // r8
  int v27; // eax
  unsigned __int16 v28; // [rsp+88h] [rbp+10h]
  int v29; // [rsp+90h] [rbp+18h]

  count = a3->count;
  v10 = a4;
  if ( (a3->Flags & 4) != 0 )
    LOWORD(count) = a5[count];
  v12 = (char *)this + 8;
  if ( a3->NameOffset )
    v13 = *(_QWORD *)v12 + a3->NameOffset;
  else
    v13 = 0;
  *(_QWORD *)a2 = v13;
  *((_QWORD *)a2 + 6) = a3;
  if ( !(_WORD)count )
  {
    *((_DWORD *)a2 + 15) = 15;
    if ( a4 < *(_DWORD *)(*(_QWORD *)v12 + 104LL) )
      *(_QWORD *)(*((_QWORD *)this + 3) + 8LL * a4) = &Ext;
    return 0;
  }
  *((_DWORD *)a2 + 15) = 8;
  *((_WORD *)a2 + 32) = count;
  OutType = a3->nonStructType.OutType;
  *((_WORD *)a2 + 33) = OutType;
  v15 = (unsigned int)(unsigned __int16)count * OutType;
  *((_DWORD *)a2 + 17) = v15;
  if ( !(_DWORD)v15 )
    return 0;
  v28 = *a6;
  ProcessHeap = GetProcessHeap();
  v17 = HeapAlloc(ProcessHeap, 8u, 80 * v15);
  *((_QWORD *)a2 + 9) = v17;
  if ( v17 )
  {
    v29 = 0;
    v19 = 0;
    v20 = 0;
    do
    {
      v21 = 0;
      *(_DWORD *)(*((_QWORD *)a2 + 9) + 80LL * v19 + 60) = 1;
      if ( *((_WORD *)a2 + 33) )
      {
        while ( 1 )
        {
          v22 = v21 + (unsigned int)a3->nonStructType.InType;
          v23 = (struct _EVENT_PROPERTY_INFO *)(*(_QWORD *)v12 + 8 * (v22 + 2 * (v22 + 7)));
          v24 = (struct _EVENT_DUMP_DATA *)(*((_QWORD *)a2 + 9) + 80LL * v19);
          result = (v23->Flags & 1) != 0
                 ? EventDumpWorkspace::ProcessComplexType(this, v24, v23, v22, a5, a6, a7)
                 : EventDumpWorkspace::ProcessSimpleType(this, v24, v23, v22, a5, a6, a7);
          if ( result )
            return result;
          ++v19;
          if ( ++v21 >= *((_WORD *)a2 + 33) )
          {
            v20 = v29;
            break;
          }
        }
      }
      v25 = *((_QWORD *)a2 + 9);
      v26 = 80LL * v19;
      v27 = *(_DWORD *)(v26 + v25 - 12);
      if ( v27 )
        *(_DWORD *)(80LL * (unsigned int)(v27 - 1) + *(_QWORD *)(v26 + v25 - 8) + 60) |= 2u;
      *(_DWORD *)(v26 + v25 - 20) |= 2u;
      LOWORD(v20) = v20 + 1;
      v29 = v20;
    }
    while ( (unsigned __int16)v20 < (unsigned __int16)count );
    if ( (unsigned int)v10 >= *(_DWORD *)(*(_QWORD *)v12 + 104LL) )
      return 0;
    result = EventDumpWorkspace::CreateHexDump(this, (unsigned __int16 **)a2 + 3, v28, *a6);
    if ( !result )
    {
      *(_QWORD *)(*((_QWORD *)this + 3) + 8 * v10) = *((_QWORD *)a2 + 3);
      return 0;
    }
  }
  else
  {
    *((_DWORD *)a2 + 17) = 0;
    return 8;
  }
  return result;
}

```

## disassembly

```asm
0x14000e540  mov     [rsp+arg_0], rbx
0x14000e545  push    rbp
0x14000e546  push    rsi
0x14000e547  push    rdi
0x14000e548  push    r12
0x14000e54a  push    r13
0x14000e54c  push    r14
0x14000e54e  push    r15
0x14000e550  sub     rsp, 40h
0x14000e554  test    byte ptr [r8], 4
0x14000e558  mov     r14, r8
0x14000e55b  movzx   edi, word ptr [r8+10h]
0x14000e560  mov     rbx, rdx
0x14000e563  mov     r12d, r9d
0x14000e566  mov     r15, rcx
0x14000e569  jz      short loc_14000E577
0x14000e56b  mov     rcx, [rsp+78h+arg_20]
0x14000e573  movzx   edi, word ptr [rcx+rdi*4]
0x14000e577  xor     ecx, ecx
0x14000e579  lea     rsi, [r15+8]
0x14000e57d  cmp     [r8+4], ecx
0x14000e581  jnz     short loc_14000E587
0x14000e583  mov     eax, ecx
0x14000e585  jmp     short loc_14000E58E
0x14000e587  mov     eax, [r8+4]
0x14000e58b  add     rax, [rsi]
0x14000e58e  mov     [rdx], rax
0x14000e591  mov     [rdx+30h], r14
0x14000e595  test    di, di
0x14000e598  jnz     short loc_14000E5C2
0x14000e59a  mov     dword ptr [rdx+3Ch], 0Fh
0x14000e5a1  mov     rax, [rsi]
0x14000e5a4  cmp     r12d, [rax+68h]
0x14000e5a8  jnb     loc_14000E787
0x14000e5ae  mov     rax, [r15+18h]
0x14000e5b2  lea     rdx, Ext
0x14000e5b9  mov     [rax+r12*8], rdx
0x14000e5bd  jmp     loc_14000E787
0x14000e5c2  mov     dword ptr [rdx+3Ch], 8
0x14000e5c9  mov     [rdx+40h], di
0x14000e5cd  movzx   eax, word ptr [r8+0Ah]
0x14000e5d2  mov     ebp, eax
0x14000e5d4  mov     [rdx+42h], ax
0x14000e5d8  movzx   eax, di
0x14000e5db  imul    ebp, eax
0x14000e5de  mov     [rdx+44h], ebp
0x14000e5e1  test    ebp, ebp
0x14000e5e3  jz      loc_14000E787
0x14000e5e9  mov     r13, [rsp+78h+arg_28]
0x14000e5f1  movzx   eax, word ptr [r13+0]
0x14000e5f6  mov     [rsp+78h+arg_8], ax
0x14000e5fe  call    cs:__imp_GetProcessHeap
0x14000e604  lea     r8, ds:0[rbp*4]
0x14000e60c  mov     rcx, rax; hHeap
0x14000e60f  add     r8, rbp
0x14000e612  mov     ebp, 8
0x14000e617  mov     edx, ebp; dwFlags
0x14000e619  shl     r8, 4; dwBytes
0x14000e61d  call    cs:__imp_HeapAlloc
0x14000e623  xor     r11d, r11d
0x14000e626  mov     [rbx+48h], rax
0x14000e62a  test    rax, rax
0x14000e62d  jnz     short loc_14000E63A
0x14000e62f  mov     [rbx+44h], r11d
0x14000e633  mov     eax, ebp
0x14000e635  jmp     loc_14000E789
0x14000e63a  mov     [rsp+78h+arg_10], r11d
0x14000e642  mov     ebp, r11d
0x14000e645  mov     r10d, r11d
0x14000e648  cmp     r11w, di
0x14000e64c  jnb     loc_14000E754
0x14000e652  mov     edx, 1
0x14000e657  movzx   eax, bp
0x14000e65a  mov     r13d, r11d
0x14000e65d  lea     rcx, [rax+rax*4]
0x14000e661  mov     rax, [rbx+48h]
0x14000e665  add     rcx, rcx
0x14000e668  mov     [rax+rcx*8+3Ch], edx
0x14000e66c  cmp     r11w, [rbx+42h]
0x14000e671  jnb     loc_14000E6FF
0x14000e677  movzx   r9d, word ptr [r14+8]
0x14000e67c  mov     rcx, r15; this
0x14000e67f  movzx   eax, r13w
0x14000e683  add     r9d, eax; unsigned int
0x14000e686  mov     rax, [rsi]
0x14000e689  lea     r8, [r9+7]
0x14000e68d  lea     r8, [r9+r8*2]
0x14000e691  lea     r8, [rax+r8*8]; struct _EVENT_PROPERTY_INFO *
0x14000e695  movzx   eax, bp
0x14000e698  lea     rdx, [rax+rax*4]
0x14000e69c  mov     al, [rsp+78h+arg_30]
0x14000e6a3  mov     [rsp+78h+var_48], al; unsigned __int8
0x14000e6a7  mov     rax, [rsp+78h+arg_28]
0x14000e6af  shl     rdx, 4
0x14000e6b3  add     rdx, [rbx+48h]; struct _EVENT_DUMP_DATA *
0x14000e6b7  test    byte ptr [r8], 1
0x14000e6bb  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x14000e6c0  mov     rax, [rsp+78h+arg_20]
0x14000e6c8  mov     [rsp+78h+var_58], rax; unsigned int *
0x14000e6cd  jz      short loc_14000E6D6
0x14000e6cf  call    ?ProcessComplexType@EventDumpWorkspace@@IEAAKPEAU_EVENT_DUMP_DATA@@PEAU_EVENT_PROPERTY_INFO@@KPEAKAEAGE@Z; EventDumpWorkspace::ProcessComplexType(_EVENT_DUMP_DATA *,_EVENT_PROPERTY_INFO *,ulong,ulong *,ushort &,uchar)
0x14000e6d4  jmp     short loc_14000E6DB
0x14000e6d6  call    ?ProcessSimpleType@EventDumpWorkspace@@IEAAKPEAU_EVENT_DUMP_DATA@@PEAU_EVENT_PROPERTY_INFO@@KPEAKAEAGE@Z; EventDumpWorkspace::ProcessSimpleType(_EVENT_DUMP_DATA *,_EVENT_PROPERTY_INFO *,ulong,ulong *,ushort &,uchar)
0x14000e6db  xor     r11d, r11d
0x14000e6de  test    eax, eax
0x14000e6e0  jnz     loc_14000E789
0x14000e6e6  lea     edx, [rax+1]
0x14000e6e9  add     bp, dx
0x14000e6ec  add     r13w, dx
0x14000e6f0  cmp     r13w, [rbx+42h]
0x14000e6f5  jb      short loc_14000E677
0x14000e6f7  mov     r10d, [rsp+78h+arg_10]
0x14000e6ff  mov     r9, [rbx+48h]
0x14000e703  movzx   eax, bp
0x14000e706  lea     r8, [rax+rax*4]
0x14000e70a  shl     r8, 4
0x14000e70e  mov     eax, [r8+r9-0Ch]
0x14000e713  test    eax, eax
0x14000e715  jz      short loc_14000E730
0x14000e717  dec     eax
0x14000e719  lea     rdx, [rax+rax*4]
0x14000e71d  mov     rax, [r8+r9-8]
0x14000e722  shl     rdx, 4
0x14000e726  or      dword ptr [rdx+rax+3Ch], 2
0x14000e72b  mov     edx, 1
0x14000e730  or      dword ptr [r8+r9-14h], 2
0x14000e736  add     r10w, dx
0x14000e73a  mov     [rsp+78h+arg_10], r10d
0x14000e742  cmp     r10w, di
0x14000e746  jb      loc_14000E657
0x14000e74c  mov     r13, [rsp+78h+arg_28]
0x14000e754  mov     rax, [rsi]
0x14000e757  cmp     r12d, [rax+68h]
0x14000e75b  jnb     short loc_14000E787
0x14000e75d  movzx   r9d, word ptr [r13+0]; unsigned __int16
0x14000e762  lea     rdx, [rbx+18h]; unsigned __int16 **
0x14000e766  movzx   r8d, [rsp+78h+arg_8]; unsigned __int16
0x14000e76f  mov     rcx, r15; this
0x14000e772  call    ?CreateHexDump@EventDumpWorkspace@@IEAAKPEAPEAGGG@Z; EventDumpWorkspace::CreateHexDump(ushort * *,ushort,ushort)
0x14000e777  test    eax, eax
0x14000e779  jnz     short loc_14000E789
0x14000e77b  mov     rcx, [r15+18h]
0x14000e77f  mov     rax, [rbx+18h]
0x14000e783  mov     [rcx+r12*8], rax
0x14000e787  xor     eax, eax
0x14000e789  mov     rbx, [rsp+78h+arg_0]
0x14000e791  add     rsp, 40h
0x14000e795  pop     r15
0x14000e797  pop     r14
0x14000e799  pop     r13
0x14000e79b  pop     r12
0x14000e79d  pop     rdi
0x14000e79e  pop     rsi
0x14000e79f  pop     rbp
0x14000e7a0  retn
```
