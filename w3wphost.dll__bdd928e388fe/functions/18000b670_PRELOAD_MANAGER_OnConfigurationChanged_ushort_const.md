# PRELOAD_MANAGER::OnConfigurationChanged(ushort const *)

- ea: `0x18000b670`
- end: `0x18000b73d`
- name: `?OnConfigurationChanged@PRELOAD_MANAGER@@UEAAJPEBG@Z`
- size: `205`
- prototype: `__int64 __fastcall(W3WP_HOST **this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180003684`
- `0x18000b670`
- `0x18000b744`
- `0x18000ba44`
- `0x18000bff8`
- `0x18000c050`

## import_xrefs

- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b6c7`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b6c7`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b696`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000b696`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000b72c`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18000b72c`

## pseudocode

```c
__int64 __fastcall PRELOAD_MANAGER::OnConfigurationChanged(W3WP_HOST **this, const unsigned __int16 *a2)
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
0x18000b670  push    rbx
0x18000b672  push    rbp
0x18000b673  push    rsi
0x18000b674  push    rdi
0x18000b675  sub     rsp, 38h
0x18000b679  mov     rbx, rcx
0x18000b67c  mov     rdi, rdx
0x18000b67f  mov     rcx, [rcx+20h]; this
0x18000b683  call    ?CheckConfigFile@W3WP_HOST@@QEAAJXZ; W3WP_HOST::CheckConfigFile(void)
0x18000b688  xor     ebp, ebp
0x18000b68a  test    eax, eax
0x18000b68c  js      loc_18000B732
0x18000b692  lea     rcx, [rbx+10h]
0x18000b696  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000b69c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b6a0  inc     rax
0x18000b6a3  cmp     [rdi+rax*2], bp
0x18000b6a7  jnz     short loc_18000B6A0
0x18000b6a9  mov     rcx, rbx; this
0x18000b6ac  cmp     rax, 17h
0x18000b6b0  ja      short loc_18000B6B9
0x18000b6b2  call    ?ProcessAllApplications@PRELOAD_MANAGER@@QEAAJXZ; PRELOAD_MANAGER::ProcessAllApplications(void)
0x18000b6b7  jmp     short loc_18000B6C1
0x18000b6b9  mov     rdx, rdi; unsigned __int16 *
0x18000b6bc  call    ?ProcessSingleApplication@PRELOAD_MANAGER@@AEAAJPEBG@Z; PRELOAD_MANAGER::ProcessSingleApplication(ushort const *)
0x18000b6c1  lea     rcx, [rbx+10h]
0x18000b6c5  mov     edi, eax
0x18000b6c7  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000b6cd  test    edi, edi
0x18000b6cf  jns     short loc_18000B732
0x18000b6d1  cmp     edi, 80004001h
0x18000b6d7  jnz     short loc_18000B6E3
0x18000b6d9  mov     rcx, rbx; this
0x18000b6dc  call    ?ReportNotImplementedWarning@PRELOAD_MANAGER@@QEAAXXZ; PRELOAD_MANAGER::ReportNotImplementedWarning(void)
0x18000b6e1  jmp     short loc_18000B732
0x18000b6e3  mov     r8d, 1
0x18000b6e9  cmp     [rbx+40h], r8d
0x18000b6ed  jnz     short loc_18000B6F9
0x18000b6ef  mov     rcx, rbx; this
0x18000b6f2  call    ?ReportWrongPipelineModeWarning@PRELOAD_MANAGER@@QEAAXXZ; PRELOAD_MANAGER::ReportWrongPipelineModeWarning(void)
0x18000b6f7  jmp     short loc_18000B732
0x18000b6f9  mov     rdx, [rbx+20h]
0x18000b6fd  cmp     [rdx+630h], ebp
0x18000b703  jnz     short loc_18000B732
0x18000b705  mov     [rsp+58h+arg_0], rbp
0x18000b70a  lea     r9, [rsp+58h+arg_0]
0x18000b70f  mov     rax, [rdx+138h]
0x18000b716  mov     [rsp+58h+var_38], edi
0x18000b71a  mov     rcx, [rax+18h]
0x18000b71e  mov     [rsp+58h+arg_0], rcx
0x18000b723  lea     rcx, [rdx+50h]
0x18000b727  mov     edx, 800008FFh
0x18000b72c  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18000b732  xor     eax, eax
0x18000b734  add     rsp, 38h
0x18000b738  pop     rdi
0x18000b739  pop     rsi
0x18000b73a  pop     rbp
0x18000b73b  pop     rbx
0x18000b73c  retn
```
