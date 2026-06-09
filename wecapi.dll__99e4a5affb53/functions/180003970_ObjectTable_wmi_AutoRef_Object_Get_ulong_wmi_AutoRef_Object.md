# ObjectTable<wmi::AutoRef<Object>>::Get(ulong,wmi::AutoRef<Object> &)

- ea: `0x180003970`
- end: `0x180003a24`
- name: `?Get@?$ObjectTable@V?$AutoRef@VObject@@@wmi@@@@QEAA_NKAEAV?$AutoRef@VObject@@@wmi@@@Z`
- size: `180`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800027ec`
- `0x180002900`
- `0x180002a14`

## callees

- `0x180003970`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003986`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003986`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003a00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003a11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003a00`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003a11`

## pseudocode

```c
char __fastcall ObjectTable<wmi::AutoRef<Object>>::Get(__int64 a1, int a2, __int64 *a3)
{
  unsigned int v5; // ecx
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rcx

  EnterCriticalSection(&g_objectTable);
  v5 = a2 - 1;
  v6 = qword_180014A38;
  v7 = *(_QWORD *)(qword_180014A38 + 8);
  if ( *(_BYTE *)(v7 + 25) )
    goto LABEL_14;
  do
  {
    if ( *(_DWORD *)(v7 + 32) >= v5 )
    {
      v6 = v7;
      v7 = *(_QWORD *)v7;
    }
    else
    {
      v7 = *(_QWORD *)(v7 + 16);
    }
  }
  while ( !*(_BYTE *)(v7 + 25) );
  if ( v6 == qword_180014A38 || v5 < *(_DWORD *)(v6 + 32) )
  {
LABEL_14:
    LeaveCriticalSection(&g_objectTable);
    return 0;
  }
  else
  {
    v8 = *(_QWORD *)(v6 + 40);
    if ( v8 )
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
    v9 = *a3;
    if ( *a3 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 8), 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(__int64, __int64))v9)(v9, 1);
    }
    *a3 = v8;
    LeaveCriticalSection(&g_objectTable);
    return 1;
  }
}

```

## disassembly

```asm
0x180003970  mov     [rsp+arg_0], rbx
0x180003975  push    rdi
0x180003976  sub     rsp, 20h
0x18000397a  lea     rcx, ?g_objectTable@@3V?$ObjectTable@V?$AutoRef@VObject@@@wmi@@@@A; lpCriticalSection
0x180003981  mov     rdi, r8
0x180003984  mov     ebx, edx
0x180003986  call    cs:__imp_EnterCriticalSection
0x18000398c  mov     rdx, cs:qword_180014A38
0x180003993  lea     ecx, [rbx-1]
0x180003996  mov     rbx, rdx
0x180003999  mov     rax, [rdx+8]
0x18000399d  cmp     byte ptr [rax+19h], 0
0x1800039a1  jnz     short loc_180003A0A
0x1800039a3  cmp     [rax+20h], ecx
0x1800039a6  jnb     short loc_1800039AE
0x1800039a8  mov     rax, [rax+10h]
0x1800039ac  jmp     short loc_1800039B4
0x1800039ae  mov     rbx, rax
0x1800039b1  mov     rax, [rax]
0x1800039b4  cmp     byte ptr [rax+19h], 0
0x1800039b8  jz      short loc_1800039A3
0x1800039ba  cmp     rbx, rdx
0x1800039bd  jz      short loc_180003A0A
0x1800039bf  cmp     ecx, [rbx+20h]
0x1800039c2  jb      short loc_180003A0A
0x1800039c4  mov     rbx, [rbx+28h]
0x1800039c8  test    rbx, rbx
0x1800039cb  jz      short loc_1800039D1
0x1800039cd  lock inc dword ptr [rbx+8]
0x1800039d1  mov     rcx, [rdi]
0x1800039d4  test    rcx, rcx
0x1800039d7  jz      short loc_1800039F6
0x1800039d9  or      eax, 0FFFFFFFFh
0x1800039dc  lock xadd [rcx+8], eax
0x1800039e1  cmp     eax, 1
0x1800039e4  jnz     short loc_1800039F6
0x1800039e6  mov     rdx, [rcx]
0x1800039e9  mov     rax, [rdx]
0x1800039ec  mov     edx, 1
0x1800039f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039f6  lea     rcx, ?g_objectTable@@3V?$ObjectTable@V?$AutoRef@VObject@@@wmi@@@@A; lpCriticalSection
0x1800039fd  mov     [rdi], rbx
0x180003a00  call    cs:__imp_LeaveCriticalSection
0x180003a06  mov     al, 1
0x180003a08  jmp     short loc_180003A19
0x180003a0a  lea     rcx, ?g_objectTable@@3V?$ObjectTable@V?$AutoRef@VObject@@@wmi@@@@A; lpCriticalSection
0x180003a11  call    cs:__imp_LeaveCriticalSection
0x180003a17  xor     al, al
0x180003a19  mov     rbx, [rsp+28h+arg_0]
0x180003a1e  add     rsp, 20h
0x180003a22  pop     rdi
0x180003a23  retn
```
