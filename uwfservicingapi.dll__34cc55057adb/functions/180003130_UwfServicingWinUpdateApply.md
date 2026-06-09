# UwfServicingWinUpdateApply

- ea: `0x180003130`
- end: `0x1800031b1`
- name: `UwfServicingWinUpdateApply`
- size: `129`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update`

## callees

- `0x180002a20`
- `0x180003130`
- `0x18000399c`

## pseudocode

```c
__int64 UwfServicingWinUpdateApply()
{
  UWFUpdateAgent *v0; // rdi
  unsigned int v1; // ebx
  __int64 v2; // rcx
  int v4; // [rsp+38h] [rbp+10h] BYREF

  v0 = qword_18000C840;
  v1 = 1;
  v4 = 0;
  do
  {
    if ( (int)UWFUpdateAgent::ApplyOnce(v0, &v4) < 0 )
      return 2;
  }
  while ( v4 == 1 );
  v2 = *((_QWORD *)qword_18000C840 + 2);
  if ( v2 )
  {
    if ( *(_DWORD *)(v2 + 20) || *(_DWORD *)(v2 + 16) )
      UwfServicingLog(1, 0, 0, L"Reboot required");
    else
      return 0;
  }
  else
  {
    return 2;
  }
  return v1;
}

```

## disassembly

```asm
0x180003130  mov     [rsp+arg_0], rbx
0x180003135  push    rdi
0x180003136  sub     rsp, 20h
0x18000313a  mov     rdi, cs:qword_18000C840
0x180003141  mov     ebx, 1
0x180003146  mov     [rsp+28h+arg_8], 0
0x18000314e  lea     rdx, [rsp+28h+arg_8]; int *
0x180003153  mov     rcx, rdi; this
0x180003156  call    ?ApplyOnce@UWFUpdateAgent@@AEAAJPEAH@Z; UWFUpdateAgent::ApplyOnce(int *)
0x18000315b  test    eax, eax
0x18000315d  js      short loc_1800031A1
0x18000315f  cmp     [rsp+28h+arg_8], ebx
0x180003163  jz      short loc_18000314E
0x180003165  mov     rax, cs:qword_18000C840
0x18000316c  mov     rcx, [rax+10h]
0x180003170  test    rcx, rcx
0x180003173  jnz     short loc_18000317A
0x180003175  lea     ebx, [rcx+2]
0x180003178  jmp     short loc_18000319D
0x18000317a  cmp     dword ptr [rcx+14h], 0
0x18000317e  jnz     short loc_18000318A
0x180003180  cmp     dword ptr [rcx+10h], 0
0x180003184  jnz     short loc_18000318A
0x180003186  xor     ebx, ebx
0x180003188  jmp     short loc_18000319D
0x18000318a  lea     r9, aRebootRequired; "Reboot required"
0x180003191  xor     r8d, r8d
0x180003194  xor     edx, edx
0x180003196  mov     ecx, ebx
0x180003198  call    ?UwfServicingLog@@YAJW4UWFSERVICING_MODULE_ID@@W4UWFSERVICING_LOG_TYPE@@KPEBGZZ; UwfServicingLog(UWFSERVICING_MODULE_ID,UWFSERVICING_LOG_TYPE,ulong,ushort const *,...)
0x18000319d  mov     eax, ebx
0x18000319f  jmp     short loc_1800031A6
0x1800031a1  mov     eax, 2
0x1800031a6  mov     rbx, [rsp+28h+arg_0]
0x1800031ab  add     rsp, 20h
0x1800031af  pop     rdi
0x1800031b0  retn
```
