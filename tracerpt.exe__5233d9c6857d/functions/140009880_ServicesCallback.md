# ServicesCallback

- ea: `0x140009880`
- end: `0x140009ac1`
- name: `ServicesCallback`
- size: `577`
- prototype: `__int64 __fastcall(PEVENT_RECORD Event)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x140003a30`

## callees

- `0x140004c2c`
- `0x140009880`
- `0x14001b8d8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009aa8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009aa8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000998d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400099f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009a61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009a9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000998d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400099f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009a61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140009a9a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000999e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009a0a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009a72`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000999e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009a0a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x140009a72`

## string_xrefs

- `0x1400098ad`: `ProcessId`
- `0x1400098fb`: `ServiceState`
- `0x14000996a`: `ServiceName`
- `0x1400099b7`: `ServiceName`

## pseudocode

```c
int __fastcall ServicesCallback(PEVENT_RECORD Event)
{
  struct _SERVICE_RECORD *v2; // rax
  struct _PROCESS_RECORD *v3; // rdx
  struct _SERVICE_RECORD *i; // rdi
  struct _SERVICE_RECORD *v5; // rbx
  unsigned int v6; // ebx
  HANDLE ProcessHeap; // rax
  unsigned int v8; // ebx
  HANDLE v9; // rax
  unsigned int v10; // ebx
  HANDLE v11; // rax
  HANDLE v12; // rax
  _DWORD v14[4]; // [rsp+20h] [rbp-10h] BYREF
  SIZE_T dwBytes; // [rsp+58h] [rbp+28h] BYREF
  unsigned int v16; // [rsp+60h] [rbp+30h] BYREF
  int v17; // [rsp+68h] [rbp+38h] BYREF

  v14[0] = 0;
  LODWORD(dwBytes) = 4;
  v16 = 0;
  v17 = 0;
  LODWORD(v2) = GetMofData(Event, L"ProcessId", v14, (unsigned int *)&dwBytes);
  if ( !(_DWORD)v2 )
  {
    LODWORD(dwBytes) = 4;
    LODWORD(v2) = GetMofData(Event, L"SubProcessTag", &v16, (unsigned int *)&dwBytes);
    if ( !(_DWORD)v2 )
    {
      LODWORD(dwBytes) = 4;
      LODWORD(v2) = GetMofData(Event, L"ServiceState", &v17, (unsigned int *)&dwBytes);
      if ( !(_DWORD)v2 )
      {
        v2 = qword_140082130;
        v3 = 0;
        while ( v2 != (struct _SERVICE_RECORD *)&qword_140082130 )
        {
          for ( i = (struct _SERVICE_RECORD *)*((_QWORD *)v2 + 4);
                i != (struct _SERVICE_RECORD *)((char *)v2 + 32);
                i = *(struct _SERVICE_RECORD **)i )
          {
            if ( v16 == *((_DWORD *)i + 8) )
              goto LABEL_14;
          }
          if ( !*((_DWORD *)v2 + 30) )
            v3 = v2;
          v2 = *(struct _SERVICE_RECORD **)v2;
        }
        v2 = AddService(v16, v3);
        i = v2;
LABEL_14:
        if ( i )
        {
          *((_DWORD *)i + 9) = v17;
          LODWORD(dwBytes) = 0;
          v5 = 0;
          if ( GetMofData(Event, L"ServiceName", 0, (unsigned int *)&dwBytes) == 122 )
          {
            v6 = dwBytes;
            ProcessHeap = GetProcessHeap();
            v2 = (struct _SERVICE_RECORD *)HeapAlloc(ProcessHeap, 8u, v6);
            v5 = v2;
            if ( !v2 )
              return (int)v2;
            if ( GetMofData(Event, L"ServiceName", v2, (unsigned int *)&dwBytes) )
              goto LABEL_24;
          }
          *((_QWORD *)i + 5) = v5;
          LODWORD(dwBytes) = 0;
          v5 = 0;
          if ( GetMofData(Event, L"DisplayName", 0, (unsigned int *)&dwBytes) == 122 )
          {
            v8 = dwBytes;
            v9 = GetProcessHeap();
            v2 = (struct _SERVICE_RECORD *)HeapAlloc(v9, 8u, v8);
            v5 = v2;
            if ( !v2 )
              return (int)v2;
            if ( GetMofData(Event, L"DisplayName", v2, (unsigned int *)&dwBytes) )
            {
LABEL_24:
              v12 = GetProcessHeap();
              LODWORD(v2) = HeapFree(v12, 0, v5);
              return (int)v2;
            }
          }
          *((_QWORD *)i + 6) = v5;
          LODWORD(dwBytes) = 0;
          v5 = 0;
          LODWORD(v2) = GetMofData(Event, L"ProcessName", 0, (unsigned int *)&dwBytes);
          if ( (_DWORD)v2 != 122 )
            goto LABEL_25;
          v10 = dwBytes;
          v11 = GetProcessHeap();
          v2 = (struct _SERVICE_RECORD *)HeapAlloc(v11, 8u, v10);
          v5 = v2;
          if ( v2 )
          {
            LODWORD(v2) = GetMofData(Event, L"ProcessName", v2, (unsigned int *)&dwBytes);
            if ( (_DWORD)v2 )
              goto LABEL_24;
LABEL_25:
            *((_QWORD *)i + 7) = v5;
          }
        }
      }
    }
  }
  return (int)v2;
}

```

## disassembly

```asm
0x140009880  mov     [rsp-18h+arg_0], rbx
0x140009885  push    rbp
0x140009886  push    rsi
0x140009887  push    rdi
0x140009888  mov     rbp, rsp
0x14000988b  sub     rsp, 30h
0x14000988f  mov     ebx, 4
0x140009894  mov     [rbp+var_10], 0
0x14000989b  lea     r9, [rbp+dwBytes]; unsigned int *
0x14000989f  mov     dword ptr [rbp+dwBytes], ebx
0x1400098a2  lea     r8, [rbp+var_10]; void *
0x1400098a6  mov     [rbp+arg_10], 0
0x1400098ad  lea     rdx, aProcessid; "ProcessId"
0x1400098b4  mov     [rbp+arg_18], 0
0x1400098bb  mov     rsi, rcx
0x1400098be  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x1400098c3  test    eax, eax
0x1400098c5  jnz     loc_140009AB4
0x1400098cb  lea     r9, [rbp+dwBytes]; unsigned int *
0x1400098cf  mov     dword ptr [rbp+dwBytes], ebx
0x1400098d2  lea     r8, [rbp+arg_10]; void *
0x1400098d6  mov     rcx, rsi; Event
0x1400098d9  lea     rdx, aSubprocesstag; "SubProcessTag"
0x1400098e0  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x1400098e5  test    eax, eax
0x1400098e7  jnz     loc_140009AB4
0x1400098ed  lea     r9, [rbp+dwBytes]; unsigned int *
0x1400098f1  mov     dword ptr [rbp+dwBytes], ebx
0x1400098f4  lea     r8, [rbp+arg_18]; void *
0x1400098f8  mov     rcx, rsi; Event
0x1400098fb  lea     rdx, aServicestate; "ServiceState"
0x140009902  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140009907  test    eax, eax
0x140009909  jnz     loc_140009AB4
0x14000990f  mov     r8d, [rbp+arg_10]
0x140009913  lea     r9, qword_140082130
0x14000991a  mov     rax, cs:qword_140082130
0x140009921  xor     edx, edx
0x140009923  jmp     short loc_140009947
0x140009925  lea     rcx, [rax+20h]
0x140009929  mov     rdi, [rcx]
0x14000992c  jmp     short loc_140009937
0x14000992e  cmp     r8d, [rdi+20h]
0x140009932  jz      short loc_140009957
0x140009934  mov     rdi, [rdi]
0x140009937  cmp     rdi, rcx
0x14000993a  jnz     short loc_14000992E
0x14000993c  cmp     dword ptr [rax+78h], 0
0x140009940  cmovz   rdx, rax; struct _PROCESS_RECORD *
0x140009944  mov     rax, [rax]
0x140009947  cmp     rax, r9
0x14000994a  jnz     short loc_140009925
0x14000994c  mov     ecx, r8d; unsigned int
0x14000994f  call    ?AddService@@YAPEAU_SERVICE_RECORD@@KPEAU_PROCESS_RECORD@@@Z; AddService(ulong,_PROCESS_RECORD *)
0x140009954  mov     rdi, rax
0x140009957  test    rdi, rdi
0x14000995a  jz      loc_140009AB4
0x140009960  mov     ecx, [rbp+arg_18]
0x140009963  lea     r9, [rbp+dwBytes]; unsigned int *
0x140009967  mov     [rdi+24h], ecx
0x14000996a  lea     rdx, aServicename; "ServiceName"
0x140009971  mov     rcx, rsi; Event
0x140009974  mov     dword ptr [rbp+dwBytes], 0
0x14000997b  xor     r8d, r8d; void *
0x14000997e  xor     ebx, ebx
0x140009980  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140009985  cmp     eax, 7Ah ; 'z'
0x140009988  jnz     short loc_1400099CE
0x14000998a  mov     ebx, dword ptr [rbp+dwBytes]
0x14000998d  call    cs:__imp_GetProcessHeap
0x140009993  mov     r8d, ebx; dwBytes
0x140009996  mov     edx, 8; dwFlags
0x14000999b  mov     rcx, rax; hHeap
0x14000999e  call    cs:__imp_HeapAlloc
0x1400099a4  mov     rbx, rax
0x1400099a7  test    rax, rax
0x1400099aa  jz      loc_140009AB4
0x1400099b0  lea     r9, [rbp+dwBytes]; unsigned int *
0x1400099b4  mov     r8, rax; void *
0x1400099b7  lea     rdx, aServicename; "ServiceName"
0x1400099be  mov     rcx, rsi; Event
0x1400099c1  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x1400099c6  test    eax, eax
0x1400099c8  jnz     loc_140009A9A
0x1400099ce  mov     [rdi+28h], rbx
0x1400099d2  lea     r9, [rbp+dwBytes]; unsigned int *
0x1400099d6  xor     r8d, r8d; void *
0x1400099d9  mov     dword ptr [rbp+dwBytes], 0
0x1400099e0  lea     rdx, aDisplayname; "DisplayName"
0x1400099e7  mov     rcx, rsi; Event
0x1400099ea  xor     ebx, ebx
0x1400099ec  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x1400099f1  cmp     eax, 7Ah ; 'z'
0x1400099f4  jnz     short loc_140009A36
0x1400099f6  mov     ebx, dword ptr [rbp+dwBytes]
0x1400099f9  call    cs:__imp_GetProcessHeap
0x1400099ff  mov     r8d, ebx; dwBytes
0x140009a02  mov     edx, 8; dwFlags
0x140009a07  mov     rcx, rax; hHeap
0x140009a0a  call    cs:__imp_HeapAlloc
0x140009a10  mov     rbx, rax
0x140009a13  test    rax, rax
0x140009a16  jz      loc_140009AB4
0x140009a1c  lea     r9, [rbp+dwBytes]; unsigned int *
0x140009a20  mov     r8, rax; void *
0x140009a23  lea     rdx, aDisplayname; "DisplayName"
0x140009a2a  mov     rcx, rsi; Event
0x140009a2d  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140009a32  test    eax, eax
0x140009a34  jnz     short loc_140009A9A
0x140009a36  mov     [rdi+30h], rbx
0x140009a3a  lea     r9, [rbp+dwBytes]; unsigned int *
0x140009a3e  xor     r8d, r8d; void *
0x140009a41  mov     dword ptr [rbp+dwBytes], 0
0x140009a48  lea     rdx, aProcessname; "ProcessName"
0x140009a4f  mov     rcx, rsi; Event
0x140009a52  xor     ebx, ebx
0x140009a54  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140009a59  cmp     eax, 7Ah ; 'z'
0x140009a5c  jnz     short loc_140009AB0
0x140009a5e  mov     ebx, dword ptr [rbp+dwBytes]
0x140009a61  call    cs:__imp_GetProcessHeap
0x140009a67  mov     r8d, ebx; dwBytes
0x140009a6a  mov     edx, 8; dwFlags
0x140009a6f  mov     rcx, rax; hHeap
0x140009a72  call    cs:__imp_HeapAlloc
0x140009a78  mov     rbx, rax
0x140009a7b  test    rax, rax
0x140009a7e  jz      short loc_140009AB4
0x140009a80  lea     r9, [rbp+dwBytes]; unsigned int *
0x140009a84  mov     r8, rax; void *
0x140009a87  lea     rdx, aProcessname; "ProcessName"
0x140009a8e  mov     rcx, rsi; Event
0x140009a91  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140009a96  test    eax, eax
0x140009a98  jz      short loc_140009AB0
0x140009a9a  call    cs:__imp_GetProcessHeap
0x140009aa0  mov     r8, rbx; lpMem
0x140009aa3  xor     edx, edx; dwFlags
0x140009aa5  mov     rcx, rax; hHeap
0x140009aa8  call    cs:__imp_HeapFree
0x140009aae  jmp     short loc_140009AB4
0x140009ab0  mov     [rdi+38h], rbx
0x140009ab4  mov     rbx, [rsp+30h+arg_0]
0x140009ab9  add     rsp, 30h
0x140009abd  pop     rdi
0x140009abe  pop     rsi
0x140009abf  pop     rbp
0x140009ac0  retn
```
