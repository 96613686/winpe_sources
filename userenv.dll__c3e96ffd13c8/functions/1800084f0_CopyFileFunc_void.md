# CopyFileFunc(void *)

- ea: `0x1800084f0`
- end: `0x1800085a7`
- name: `?CopyFileFunc@@YAKPEAX@Z`
- size: `183`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000bdd8`

## callees

- `0x180006904`
- `0x1800084f0`
- `0x1800085b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008509`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180008509`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000851c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000851c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008558`

## pseudocode

```c
__int64 __fastcall CopyFileFunc(_DWORD *Parameter)
{
  __int64 v2; // rbx
  DWORD dwMessageId; // eax

  v2 = 0;
  while ( 1 )
  {
    WaitForSingleObject(*(HANDLE *)(*(_QWORD *)Parameter + 8LL), 0xFFFFFFFF);
    if ( !Parameter[2] )
    {
      do
      {
        v2 = *(_QWORD *)(*(_QWORD *)Parameter + 16LL);
        if ( !v2 )
          break;
        *(_QWORD *)(*(_QWORD *)Parameter + 16LL) = *(_QWORD *)(v2 + 48);
      }
      while ( *(_DWORD *)(v2 + 44) );
    }
    SetEvent(*(HANDLE *)(*(_QWORD *)Parameter + 8LL));
    if ( Parameter[2] || !v2 )
      break;
    if ( !(unsigned int)ReconcileFile(
                          *(LPCWSTR *)v2,
                          *(LPCWSTR *)(v2 + 8),
                          **(_DWORD **)Parameter,
                          (struct _FILETIME *)(v2 + 16),
                          0,
                          0) )
    {
      dwMessageId = GetLastError();
      CCopyError::Report(
        *(CCopyError **)(*(_QWORD *)Parameter + 32LL),
        *(void **)(*(_QWORD *)Parameter + 24LL),
        *(const unsigned __int16 **)v2,
        *(const unsigned __int16 **)(v2 + 8),
        dwMessageId);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800084f0  mov     [rsp+arg_0], rbx
0x1800084f5  push    rdi
0x1800084f6  sub     rsp, 30h
0x1800084fa  mov     rdi, rcx
0x1800084fd  xor     ebx, ebx
0x1800084ff  mov     rcx, [rdi]
0x180008502  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180008505  mov     rcx, [rcx+8]; hHandle
0x180008509  call    cs:__imp_WaitForSingleObject
0x18000850f  cmp     dword ptr [rdi+8], 0
0x180008513  jz      short loc_18000857B
0x180008515  mov     rcx, [rdi]
0x180008518  mov     rcx, [rcx+8]; hEvent
0x18000851c  call    cs:__imp_SetEvent
0x180008522  cmp     dword ptr [rdi+8], 0
0x180008526  jnz     short loc_18000859A
0x180008528  test    rbx, rbx
0x18000852b  jz      short loc_18000859A
0x18000852d  mov     r8, [rdi]
0x180008530  lea     r9, [rbx+10h]; struct _FILETIME *
0x180008534  mov     rdx, [rbx+8]; LPCWSTR
0x180008538  mov     rcx, [rbx]; lpFileName
0x18000853b  mov     [rsp+38h+var_10], 0; int
0x180008543  mov     r8d, [r8]; unsigned int
0x180008546  mov     qword ptr [rsp+38h+dwMessageId], 0; struct _FILETIME *
0x18000854f  call    ?ReconcileFile@@YAHPEBG0KPEAU_FILETIME@@1H@Z; ReconcileFile(ushort const *,ushort const *,ulong,_FILETIME *,_FILETIME *,int)
0x180008554  test    eax, eax
0x180008556  jnz     short loc_1800084FF
0x180008558  call    cs:__imp_GetLastError
0x18000855e  mov     rcx, [rdi]
0x180008561  mov     r9, [rbx+8]; unsigned __int16 *
0x180008565  mov     r8, [rbx]; unsigned __int16 *
0x180008568  mov     [rsp+38h+dwMessageId], eax; dwMessageId
0x18000856c  mov     rdx, [rcx+18h]; void *
0x180008570  mov     rcx, [rcx+20h]; this
0x180008574  call    ?Report@CCopyError@@QEAAJPEAXPEBG1K@Z; CCopyError::Report(void *,ushort const *,ushort const *,ulong)
0x180008579  jmp     short loc_1800084FF
0x18000857b  mov     rcx, [rdi]
0x18000857e  mov     rbx, [rcx+10h]
0x180008582  test    rbx, rbx
0x180008585  jz      short loc_180008515
0x180008587  mov     rax, [rbx+30h]
0x18000858b  mov     [rcx+10h], rax
0x18000858f  cmp     dword ptr [rbx+2Ch], 0
0x180008593  jnz     short loc_18000857B
0x180008595  jmp     loc_180008515
0x18000859a  mov     rbx, [rsp+38h+arg_0]
0x18000859f  xor     eax, eax
0x1800085a1  add     rsp, 30h
0x1800085a5  pop     rdi
0x1800085a6  retn
```
