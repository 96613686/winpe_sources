# VidXSchedulerVpEnlightenmentTeardown

- ea: `0x1400760d4`
- end: `0x140076175`
- name: `VidXSchedulerVpEnlightenmentTeardown`
- size: `161`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14009afbc`
- `0x14009b3cc`
- `0x1400fa928`

## callees

- `0x14000f8d4`
- `0x1400760d4`
- `0x14009b600`

## import_xrefs

- `winhvr!WinHvConfigureSchedulerAssistNotifications` at `0x140076113`
- `winhvr!WinHvConfigureSchedulerAssistNotifications` at `0x140076113`
- `winhvr!WinHvSetSchedulerAssistData` at `0x14007612f`
- `winhvr!WinHvSetSchedulerAssistData` at `0x14007612f`

## pseudocode

```c
void __fastcall VidXSchedulerVpEnlightenmentTeardown(_QWORD *a1)
{
  __int64 v1; // rdi
  _DWORD *v3; // rax
  __int64 v4; // rsi

  v1 = a1[48];
  if ( v1 )
  {
    v3 = *(_DWORD **)(v1 + 40);
    if ( v3 )
    {
      if ( *v3 == 1 )
      {
        WinHvConfigureSchedulerAssistNotifications(*(_QWORD *)(*a1 + 648LL), *((unsigned int *)a1 + 2), 0, 0);
        WinHvSetSchedulerAssistData(*(_QWORD *)(*a1 + 648LL), *((unsigned int *)a1 + 2), 0);
        v4 = *(_QWORD *)(v1 + 40);
        *(_QWORD *)(v1 + 40) = 0;
        if ( a1[42] )
          VidXSchedulerpSetThreadSchedulerAssist(a1);
        VidXSchedulerpVpAssistContextTeardown(*a1, v4);
      }
    }
  }
}

```

## disassembly

```asm
0x1400760d4  mov     [rsp+arg_0], rbx
0x1400760d9  mov     [rsp+arg_8], rsi
0x1400760de  push    rdi
0x1400760df  sub     rsp, 20h
0x1400760e3  mov     rdi, [rcx+180h]
0x1400760ea  mov     rbx, rcx
0x1400760ed  test    rdi, rdi
0x1400760f0  jz      short loc_140076164
0x1400760f2  mov     rax, [rdi+28h]
0x1400760f6  test    rax, rax
0x1400760f9  jz      short loc_140076164
0x1400760fb  cmp     dword ptr [rax], 1
0x1400760fe  jnz     short loc_140076164
0x140076100  mov     rcx, [rcx]
0x140076103  xor     r9d, r9d
0x140076106  mov     edx, [rbx+8]
0x140076109  xor     r8d, r8d
0x14007610c  mov     rcx, [rcx+288h]
0x140076113  call    cs:__imp_WinHvConfigureSchedulerAssistNotifications
0x14007611a  nop     dword ptr [rax+rax+00h]
0x14007611f  mov     rcx, [rbx]
0x140076122  xor     r8d, r8d
0x140076125  mov     edx, [rbx+8]
0x140076128  mov     rcx, [rcx+288h]
0x14007612f  call    cs:__imp_WinHvSetSchedulerAssistData
0x140076136  nop     dword ptr [rax+rax+00h]
0x14007613b  mov     rsi, [rdi+28h]
0x14007613f  mov     qword ptr [rdi+28h], 0
0x140076147  cmp     qword ptr [rbx+150h], 0
0x14007614f  jz      short loc_140076159
0x140076151  mov     rcx, rbx
0x140076154  call    VidXSchedulerpSetThreadSchedulerAssist
0x140076159  mov     rcx, [rbx]
0x14007615c  mov     rdx, rsi
0x14007615f  call    VidXSchedulerpVpAssistContextTeardown
0x140076164  mov     rbx, [rsp+28h+arg_0]
0x140076169  mov     rsi, [rsp+28h+arg_8]
0x14007616e  add     rsp, 20h
0x140076172  pop     rdi
0x140076173  retn
```
