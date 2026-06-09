# CWMFileSinkV1::InternalClose(void)

- ea: `0x180009630`
- end: `0x180009814`
- name: `?InternalClose@CWMFileSinkV1@@MEAAJXZ`
- size: `484`
- prototype: `__int64 __fastcall(CWMFileSinkV1 *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180003440`

## callees

- `0x180007f74`
- `0x180009630`
- `0x18000bddc`
- `0x18000c230`
- `0x18000cb10`
- `0x18000d094`
- `0x18002b010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800097af`
- `KERNEL32!CloseHandle` at `0x1800097e4`
- `KERNEL32!CloseHandle` at `0x1800097af`
- `KERNEL32!CloseHandle` at `0x1800097e4`
- `KERNEL32!SetFilePointer` at `0x180009732`
- `KERNEL32!SetFilePointer` at `0x180009732`
- `KERNEL32!LeaveCriticalSection` at `0x1800097f9`
- `KERNEL32!LeaveCriticalSection` at `0x1800097f9`
- `KERNEL32!WriteFile` at `0x180009763`
- `KERNEL32!WriteFile` at `0x180009763`
- `KERNEL32!EnterCriticalSection` at `0x180009649`
- `KERNEL32!EnterCriticalSection` at `0x180009649`

## pseudocode

```c
__int64 __fastcall CWMFileSinkV1::InternalClose(CWMFileSinkV1 *this)
{
  int updated; // edi
  CUnbufferedWriter *v3; // rcx
  unsigned int v4; // edx
  DWORD v5; // eax
  __int64 v6; // rsi
  void *v7; // rcx
  CUnbufferedWriter *v8; // rcx
  void *v9; // rcx
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp+8h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( !*((_QWORD *)this + 25) )
  {
    updated = -1072889813;
    goto LABEL_32;
  }
  if ( !*((_DWORD *)this + 9) )
  {
    if ( *((_QWORD *)this + 24) != -1 )
      goto LABEL_6;
LABEL_15:
    updated = 1;
    goto LABEL_32;
  }
  v3 = (CUnbufferedWriter *)*((_QWORD *)this + 1158);
  if ( !v3 )
    goto LABEL_15;
  CUnbufferedWriter::EndWriting(v3);
LABEL_6:
  updated = 0;
  if ( *((_DWORD *)this + 6) || !*((_DWORD *)this + 5) || (updated = CWMFileSinkV1::WriteHeader(this), updated >= 0) )
  {
    (*(void (__fastcall **)(CWMFileSinkV1 *))(*(_QWORD *)this + 240LL))(this);
    if ( !*((_DWORD *)this + 5) )
      goto LABEL_22;
    updated = CWMFileSinkV1::UpdateHeader(this);
    if ( updated < 0 )
      goto LABEL_23;
    NumberOfBytesWritten = 0;
    if ( *((_DWORD *)this + 9) )
    {
      updated = CUnbufferedWriter::RewriteHeader(
                  *((CUnbufferedWriter **)this + 1158),
                  *((unsigned __int8 **)this + 29),
                  *((_DWORD *)this + 56));
      v5 = updated >= 0 ? *((_DWORD *)this + 56) : 0;
    }
    else
    {
      if ( SetFilePointer(*((HANDLE *)this + 24), 0, 0, 0) == -1 )
      {
        updated = -2147418113;
        goto LABEL_23;
      }
      WriteFile(*((HANDLE *)this + 24), *((LPCVOID *)this + 29), *((_DWORD *)this + 56), &NumberOfBytesWritten, 0);
      v5 = NumberOfBytesWritten;
    }
    if ( v5 == *((_DWORD *)this + 56) )
    {
LABEL_22:
      *((_DWORD *)this + 6) = 0;
    }
    else
    {
      *((_DWORD *)this + 2314) = 1;
      updated = -1072889832;
    }
  }
LABEL_23:
  if ( *((_DWORD *)this + 9) )
  {
    v6 = *((_QWORD *)this + 1158);
    if ( !*(_DWORD *)(v6 + 64) )
      CUnbufferedWriter::EndWriting(*((CUnbufferedWriter **)this + 1158));
    v7 = *(void **)(v6 + 24);
    if ( v7 != (void *)-1LL )
    {
      CloseHandle(v7);
      *(_QWORD *)(v6 + 24) = -1;
    }
    v8 = (CUnbufferedWriter *)*((_QWORD *)this + 1158);
    if ( v8 )
    {
      CUnbufferedWriter::`scalar deleting destructor'(v8, v4);
      *((_QWORD *)this + 1158) = 0;
    }
  }
  else
  {
    v9 = (void *)*((_QWORD *)this + 24);
    if ( v9 != (void *)-1LL )
    {
      CloseHandle(v9);
      *((_QWORD *)this + 24) = -1;
    }
  }
LABEL_32:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180009630  mov     [rsp+arg_8], rbx
0x180009635  mov     [rsp+arg_10], rbp
0x18000963a  push    rsi
0x18000963b  push    rdi
0x18000963c  push    r14
0x18000963e  sub     rsp, 30h
0x180009642  mov     rbx, rcx
0x180009645  add     rcx, 30h ; '0'; lpCriticalSection
0x180009649  call    cs:__imp_EnterCriticalSection
0x18000964f  xor     r14d, r14d
0x180009652  cmp     [rbx+0C8h], r14
0x180009659  jnz     short loc_180009665
0x18000965b  mov     edi, 0C00D002Bh
0x180009660  jmp     loc_1800097F5
0x180009665  cmp     [rbx+24h], r14d
0x180009669  jz      loc_180009703
0x18000966f  mov     rcx, [rbx+2430h]; this
0x180009676  test    rcx, rcx
0x180009679  jz      loc_180009711
0x18000967f  call    ?EndWriting@CUnbufferedWriter@@QEAAJXZ; CUnbufferedWriter::EndWriting(void)
0x180009684  mov     edi, r14d
0x180009687  cmp     [rbx+18h], r14d
0x18000968b  jnz     short loc_1800096A5
0x18000968d  cmp     [rbx+14h], r14d
0x180009691  jz      short loc_1800096A5
0x180009693  mov     rcx, rbx; this
0x180009696  call    ?WriteHeader@CWMFileSinkV1@@IEAAJXZ; CWMFileSinkV1::WriteHeader(void)
0x18000969b  mov     edi, eax
0x18000969d  test    eax, eax
0x18000969f  js      loc_18000978A
0x1800096a5  mov     rcx, [rbx]
0x1800096a8  mov     rax, [rcx+0F0h]
0x1800096af  mov     rcx, rbx
0x1800096b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096b7  cmp     [rbx+14h], r14d
0x1800096bb  jz      loc_180009786
0x1800096c1  mov     rcx, rbx; this
0x1800096c4  call    ?UpdateHeader@CWMFileSinkV1@@IEAAJXZ; CWMFileSinkV1::UpdateHeader(void)
0x1800096c9  mov     edi, eax
0x1800096cb  test    eax, eax
0x1800096cd  js      loc_18000978A
0x1800096d3  mov     [rsp+48h+NumberOfBytesWritten], r14d
0x1800096d8  cmp     [rbx+24h], r14d
0x1800096dc  jz      short loc_180009723
0x1800096de  mov     r8d, [rbx+0E0h]; unsigned int
0x1800096e5  mov     rdx, [rbx+0E8h]; unsigned __int8 *
0x1800096ec  mov     rcx, [rbx+2430h]; this
0x1800096f3  call    ?RewriteHeader@CUnbufferedWriter@@QEAAJPEAEK@Z; CUnbufferedWriter::RewriteHeader(uchar *,ulong)
0x1800096f8  mov     edi, eax
0x1800096fa  test    eax, eax
0x1800096fc  jns     short loc_18000971B
0x1800096fe  mov     eax, r14d
0x180009701  jmp     short loc_18000976D
0x180009703  cmp     qword ptr [rbx+0C0h], 0FFFFFFFFFFFFFFFFh
0x18000970b  jnz     loc_180009684
0x180009711  mov     edi, 1
0x180009716  jmp     loc_1800097F5
0x18000971b  mov     eax, [rbx+0E0h]
0x180009721  jmp     short loc_18000976D
0x180009723  mov     rcx, [rbx+0C0h]; hFile
0x18000972a  xor     r9d, r9d; dwMoveMethod
0x18000972d  xor     r8d, r8d; lpDistanceToMoveHigh
0x180009730  xor     edx, edx; lDistanceToMove
0x180009732  call    cs:__imp_SetFilePointer
0x180009738  cmp     eax, 0FFFFFFFFh
0x18000973b  jnz     short loc_180009744
0x18000973d  mov     edi, 8000FFFFh
0x180009742  jmp     short loc_18000978A
0x180009744  mov     r8d, [rbx+0E0h]; nNumberOfBytesToWrite
0x18000974b  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180009750  mov     rdx, [rbx+0E8h]; lpBuffer
0x180009757  mov     rcx, [rbx+0C0h]; hFile
0x18000975e  mov     [rsp+48h+lpOverlapped], r14; lpOverlapped
0x180009763  call    cs:__imp_WriteFile
0x180009769  mov     eax, [rsp+48h+NumberOfBytesWritten]
0x18000976d  cmp     eax, [rbx+0E0h]
0x180009773  jz      short loc_180009786
0x180009775  mov     dword ptr [rbx+2428h], 1
0x18000977f  mov     edi, 0C00D0018h
0x180009784  jmp     short loc_18000978A
0x180009786  mov     [rbx+18h], r14d
0x18000978a  cmp     [rbx+24h], r14d
0x18000978e  jz      short loc_1800097D7
0x180009790  mov     rsi, [rbx+2430h]
0x180009797  cmp     [rsi+40h], r14d
0x18000979b  jnz     short loc_1800097A5
0x18000979d  mov     rcx, rsi; this
0x1800097a0  call    ?EndWriting@CUnbufferedWriter@@QEAAJXZ; CUnbufferedWriter::EndWriting(void)
0x1800097a5  mov     rcx, [rsi+18h]; hObject
0x1800097a9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800097ad  jz      short loc_1800097BD
0x1800097af  call    cs:__imp_CloseHandle
0x1800097b5  mov     qword ptr [rsi+18h], 0FFFFFFFFFFFFFFFFh
0x1800097bd  mov     rcx, [rbx+2430h]; this
0x1800097c4  test    rcx, rcx
0x1800097c7  jz      short loc_1800097F5
0x1800097c9  call    ??_GCUnbufferedWriter@@QEAAPEAXI@Z; CUnbufferedWriter::`scalar deleting destructor'(uint)
0x1800097ce  mov     [rbx+2430h], r14
0x1800097d5  jmp     short loc_1800097F5
0x1800097d7  mov     rcx, [rbx+0C0h]; hObject
0x1800097de  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800097e2  jz      short loc_1800097F5
0x1800097e4  call    cs:__imp_CloseHandle
0x1800097ea  mov     qword ptr [rbx+0C0h], 0FFFFFFFFFFFFFFFFh
0x1800097f5  lea     rcx, [rbx+30h]; lpCriticalSection
0x1800097f9  call    cs:__imp_LeaveCriticalSection
0x1800097ff  mov     rbx, [rsp+48h+arg_8]
0x180009804  mov     eax, edi
0x180009806  mov     rbp, [rsp+48h+arg_10]
0x18000980b  add     rsp, 30h
0x18000980f  pop     r14
0x180009811  pop     rdi
0x180009812  pop     rsi
0x180009813  retn
```
