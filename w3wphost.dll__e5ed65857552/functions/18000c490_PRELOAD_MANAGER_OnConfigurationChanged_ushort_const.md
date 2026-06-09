# PRELOAD_MANAGER::OnConfigurationChanged(ushort const *)

- ea: `0x18000c490`
- end: `0x18000c570`
- name: `?OnConfigurationChanged@PRELOAD_MANAGER@@UEAAJPEBG@Z`
- size: `224`
- prototype: `__int64 __fastcall(PRELOAD_MANAGER *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180003914`
- `0x18000c490`
- `0x18000c578`
- `0x18000c88c`
- `0x18000cec8`
- `0x18000cf28`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c4ed`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c4ed`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c4b6`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000c4b6`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000c558`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000c558`

## pseudocode

```c
__int64 __fastcall PRELOAD_MANAGER::OnConfigurationChanged(W3WP_HOST **this, unsigned __int16 *a2)
{
  unsigned __int64 v4; // rax
  signed int v5; // eax
  signed int v6; // edi
  W3WP_HOST *v7; // rdx
  const unsigned __int16 *v9; // [rsp+60h] [rbp+8h] BYREF

  if ( (int)W3WP_HOST::CheckConfigFile(this[4]) >= 0 )
  {
    CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(this + 2));
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
    v5 = v4 > 0x17
       ? PRELOAD_MANAGER::ProcessSingleApplication((PRELOAD_MANAGER *)this, a2)
       : PRELOAD_MANAGER::ProcessAllApplications((PRELOAD_MANAGER *)this);
    v6 = v5;
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(this + 2));
    if ( v6 < 0 )
    {
      if ( v6 == -2147467263 )
      {
        PRELOAD_MANAGER::ReportNotImplementedWarning((PRELOAD_MANAGER *)this);
      }
      else if ( *((_DWORD *)this + 16) == 1 )
      {
        PRELOAD_MANAGER::ReportWrongPipelineModeWarning((PRELOAD_MANAGER *)this);
      }
      else
      {
        v7 = this[4];
        if ( !*((_DWORD *)v7 + 396) )
        {
          v9 = 0;
          v9 = *(const unsigned __int16 **)(*((_QWORD *)v7 + 39) + 24LL);
          EVENT_LOG::LogEvent((W3WP_HOST *)((char *)v7 + 80), 0x800008FF, 1u, &v9, v6);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000c490  push    rbx
0x18000c492  push    rbp
0x18000c493  push    rsi
0x18000c494  push    rdi
0x18000c495  sub     rsp, 38h
0x18000c499  mov     rbx, rcx
0x18000c49c  mov     rdi, rdx
0x18000c49f  mov     rcx, [rcx+20h]; this
0x18000c4a3  call    ?CheckConfigFile@W3WP_HOST@@QEAAJXZ; W3WP_HOST::CheckConfigFile(void)
0x18000c4a8  xor     ebp, ebp
0x18000c4aa  test    eax, eax
0x18000c4ac  js      loc_18000C564
0x18000c4b2  lea     rcx, [rbx+10h]
0x18000c4b6  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000c4bd  nop     dword ptr [rax+rax+00h]
0x18000c4c2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c4c6  inc     rax
0x18000c4c9  cmp     [rdi+rax*2], bp
0x18000c4cd  jnz     short loc_18000C4C6
0x18000c4cf  mov     rcx, rbx; this
0x18000c4d2  cmp     rax, 17h
0x18000c4d6  ja      short loc_18000C4DF
0x18000c4d8  call    ?ProcessAllApplications@PRELOAD_MANAGER@@QEAAJXZ; PRELOAD_MANAGER::ProcessAllApplications(void)
0x18000c4dd  jmp     short loc_18000C4E7
0x18000c4df  mov     rdx, rdi; unsigned __int16 *
0x18000c4e2  call    ?ProcessSingleApplication@PRELOAD_MANAGER@@AEAAJPEBG@Z; PRELOAD_MANAGER::ProcessSingleApplication(ushort const *)
0x18000c4e7  lea     rcx, [rbx+10h]
0x18000c4eb  mov     edi, eax
0x18000c4ed  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000c4f4  nop     dword ptr [rax+rax+00h]
0x18000c4f9  test    edi, edi
0x18000c4fb  jns     short loc_18000C564
0x18000c4fd  cmp     edi, 80004001h
0x18000c503  jnz     short loc_18000C50F
0x18000c505  mov     rcx, rbx; this
0x18000c508  call    ?ReportNotImplementedWarning@PRELOAD_MANAGER@@QEAAXXZ; PRELOAD_MANAGER::ReportNotImplementedWarning(void)
0x18000c50d  jmp     short loc_18000C564
0x18000c50f  mov     r8d, 1
0x18000c515  cmp     [rbx+40h], r8d
0x18000c519  jnz     short loc_18000C525
0x18000c51b  mov     rcx, rbx; this
0x18000c51e  call    ?ReportWrongPipelineModeWarning@PRELOAD_MANAGER@@QEAAXXZ; PRELOAD_MANAGER::ReportWrongPipelineModeWarning(void)
0x18000c523  jmp     short loc_18000C564
0x18000c525  mov     rdx, [rbx+20h]
0x18000c529  cmp     [rdx+630h], ebp
0x18000c52f  jnz     short loc_18000C564
0x18000c531  mov     [rsp+58h+arg_0], rbp
0x18000c536  lea     r9, [rsp+58h+arg_0]
0x18000c53b  mov     rax, [rdx+138h]
0x18000c542  mov     [rsp+58h+var_38], edi
0x18000c546  mov     rcx, [rax+18h]
0x18000c54a  mov     [rsp+58h+arg_0], rcx
0x18000c54f  lea     rcx, [rdx+50h]
0x18000c553  mov     edx, 800008FFh
0x18000c558  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000c55f  nop     dword ptr [rax+rax+00h]
0x18000c564  xor     eax, eax
0x18000c566  add     rsp, 38h
0x18000c56a  pop     rdi
0x18000c56b  pop     rsi
0x18000c56c  pop     rbp
0x18000c56d  pop     rbx
0x18000c56e  retn
```
