# WimSetThreadIsInMessageCallback

- ea: `0x180010440`
- end: `0x180010502`
- name: `WimSetThreadIsInMessageCallback`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800100c8`

## callees

- `0x180010440`
- `0x18002188c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180010453`
- `KERNEL32!GetCurrentThreadId` at `0x180010453`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001048c`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001048c`
- `ntdll!RtlReleaseResource` at `0x1800104e4`
- `ntdll!RtlReleaseResource` at `0x1800104e4`

## pseudocode

```c
void __fastcall WimSetThreadIsInMessageCallback(__int64 *a1, int a2)
{
  _QWORD *v4; // rax
  __int64 *v5; // rax
  __int64 **v6; // rdx

  if ( a2 )
    *((_DWORD *)a1 + 4) = GetCurrentThreadId();
  if ( (int)WimLazyInitialize(InitializeGlobalRwLock_Callback, DeleteGlobalRwLock_Callback, 0, &dword_18007788C) >= 0 )
  {
    RtlAcquireResourceExclusive(&Resource, 1u);
    if ( a2 )
    {
      v4 = off_180077048;
      if ( *((_UNKNOWN ***)off_180077048 + 1) == &off_180077048 )
      {
        *a1 = (__int64)off_180077048;
        a1[1] = (__int64)&off_180077048;
        v4[1] = a1;
        off_180077048 = a1;
LABEL_10:
        RtlReleaseResource(&Resource);
        return;
      }
    }
    else
    {
      v5 = (__int64 *)*a1;
      if ( *(__int64 **)(*a1 + 8) == a1 )
      {
        v6 = (__int64 **)a1[1];
        if ( *v6 == a1 )
        {
          *v6 = v5;
          v5[1] = (__int64)v6;
          goto LABEL_10;
        }
      }
    }
    __fastfail(3u);
  }
}

```

## disassembly

```asm
0x180010440  mov     [rsp+arg_0], rbx
0x180010445  push    rdi
0x180010446  sub     rsp, 20h
0x18001044a  mov     edi, edx
0x18001044c  mov     rbx, rcx
0x18001044f  test    edx, edx
0x180010451  jz      short loc_180010462
0x180010453  call    cs:__imp_GetCurrentThreadId
0x18001045a  nop     dword ptr [rax+rax+00h]
0x18001045f  mov     [rbx+10h], eax
0x180010462  lea     r9, dword_18007788C
0x180010469  xor     r8d, r8d
0x18001046c  lea     rdx, DeleteGlobalRwLock_Callback
0x180010473  lea     rcx, InitializeGlobalRwLock_Callback
0x18001047a  call    WimLazyInitialize
0x18001047f  test    eax, eax
0x180010481  js      short loc_1800104F0
0x180010483  mov     dl, 1; Wait
0x180010485  lea     rcx, Resource; Resource
0x18001048c  call    cs:__imp_RtlAcquireResourceExclusive
0x180010493  nop     dword ptr [rax+rax+00h]
0x180010498  test    edi, edi
0x18001049a  jz      short loc_1800104C4
0x18001049c  mov     rax, cs:off_180077048
0x1800104a3  lea     rcx, off_180077048
0x1800104aa  cmp     [rax+8], rcx
0x1800104ae  jnz     short loc_1800104FB
0x1800104b0  mov     [rbx], rax
0x1800104b3  mov     [rbx+8], rcx
0x1800104b7  mov     [rax+8], rbx
0x1800104bb  mov     cs:off_180077048, rbx
0x1800104c2  jmp     short loc_1800104DD
0x1800104c4  mov     rax, [rbx]
0x1800104c7  cmp     [rax+8], rbx
0x1800104cb  jnz     short loc_1800104FB
0x1800104cd  mov     rdx, [rbx+8]
0x1800104d1  cmp     [rdx], rbx
0x1800104d4  jnz     short loc_1800104FB
0x1800104d6  mov     [rdx], rax
0x1800104d9  mov     [rax+8], rdx
0x1800104dd  lea     rcx, Resource; Resource
0x1800104e4  call    cs:__imp_RtlReleaseResource
0x1800104eb  nop     dword ptr [rax+rax+00h]
0x1800104f0  mov     rbx, [rsp+28h+arg_0]
0x1800104f5  add     rsp, 20h
0x1800104f9  pop     rdi
0x1800104fa  retn
0x1800104fb  mov     ecx, 3
0x180010500  int     29h; Win8: RtlFailFast(ecx)
```
