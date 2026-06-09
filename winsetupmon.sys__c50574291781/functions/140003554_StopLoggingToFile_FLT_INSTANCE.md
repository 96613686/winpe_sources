# StopLoggingToFile(_FLT_INSTANCE *)

- ea: `0x140003554`
- end: `0x140003625`
- name: `?StopLoggingToFile@@YAXPEAU_FLT_INSTANCE@@@Z`
- size: `209`
- prototype: `void __fastcall(struct _FLT_INSTANCE *)`
- caller_count: `5`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14001e808`
- `0x14001f6c0`
- `0x14001fab0`
- `0x14001fe30`
- `0x14001ffd0`

## callees

- `0x140002488`
- `0x140003554`
- `0x140003944`
- `0x1400040b4`
- `0x14000dd90`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x1400035a4`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400035a4`

## pseudocode

```c
void __fastcall StopLoggingToFile(struct _FLT_INSTANCE *a1)
{
  __int64 v1; // rdi
  int v2; // eax
  __int64 v3; // rbx
  int v4; // esi
  __int64 v5; // r8
  __int64 v6; // rcx

  if ( Instance )
  {
    if ( a1 )
    {
      if ( a1 != Instance )
        return;
    }
    else
    {
      v1 = MEMORY[0xFFFFF78000000320];
      v2 = FlushVolume(0, (struct _FLT_INSTANCE *)Instance);
      v3 = MEMORY[0xFFFFF78000000320];
      v4 = v2;
      v5 = 100 * (v3 - v1) * KeQueryTimeIncrement() / 1000000;
      if ( v4 < 0 )
        WriteLogMessage(
          3,
          L"WinSetupMon::StopLoggingToFile: FlushVolume took %I64d ms and failed (0x%08X)",
          v5,
          (unsigned int)v4);
      else
        WriteLogMessage(1, L"Flushed log volume; took %I64d ms", v5);
    }
    WriteLogStop();
    LOBYTE(v6) = 1;
    CloseLog(v6, 0);
  }
}

```

## disassembly

```asm
0x140003554  mov     [rsp+arg_0], rbx
0x140003559  mov     [rsp+arg_8], rsi
0x14000355e  push    rdi
0x14000355f  sub     rsp, 20h
0x140003563  mov     rax, cs:Instance
0x14000356a  test    rax, rax
0x14000356d  jz      loc_140003614
0x140003573  test    rcx, rcx
0x140003576  jz      short loc_140003586
0x140003578  cmp     rcx, rax
0x14000357b  jnz     loc_140003614
0x140003581  jmp     loc_140003606
0x140003586  mov     rbx, 0FFFFF78000000320h
0x140003590  mov     rdi, [rbx]
0x140003593  mov     rdx, cs:Instance; struct _FLT_INSTANCE *
0x14000359a  call    ?FlushVolume@@YAJPEAU_FLT_FILTER@@PEAU_FLT_INSTANCE@@@Z; FlushVolume(_FLT_FILTER *,_FLT_INSTANCE *)
0x14000359f  mov     rbx, [rbx]
0x1400035a2  mov     esi, eax
0x1400035a4  call    cs:__imp_KeQueryTimeIncrement
0x1400035ab  nop     dword ptr [rax+rax+00h]
0x1400035b0  mov     ecx, eax
0x1400035b2  sub     rbx, rdi
0x1400035b5  imul    rcx, rbx
0x1400035b9  mov     rax, 431BDE82D7B634DBh
0x1400035c3  imul    rcx, 64h ; 'd'
0x1400035c7  imul    rcx
0x1400035ca  sar     rdx, 12h
0x1400035ce  mov     rcx, rdx
0x1400035d1  shr     rcx, 3Fh
0x1400035d5  add     rdx, rcx
0x1400035d8  mov     r8, rdx
0x1400035db  test    esi, esi
0x1400035dd  js      short loc_1400035F2
0x1400035df  lea     rdx, aFlushedLogVolu; "Flushed log volume; took %I64d ms"
0x1400035e6  mov     ecx, 1
0x1400035eb  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x1400035f0  jmp     short loc_140003606
0x1400035f2  mov     r9d, esi
0x1400035f5  lea     rdx, aWinsetupmonSto; "WinSetupMon::StopLoggingToFile: FlushVo"...
0x1400035fc  mov     ecx, 3
0x140003601  call    ?WriteLogMessage@@YAXW4_LOG_LEVEL@@PEBGZZ; WriteLogMessage(_LOG_LEVEL,ushort const *,...)
0x140003606  call    ?WriteLogStop@@YAXXZ; WriteLogStop(void)
0x14000360b  xor     edx, edx
0x14000360d  mov     cl, 1
0x14000360f  call    CloseLog
0x140003614  mov     rbx, [rsp+28h+arg_0]
0x140003619  mov     rsi, [rsp+28h+arg_8]
0x14000361e  add     rsp, 20h
0x140003622  pop     rdi
0x140003623  retn
```
