# VidXSchedulerVpEnlightenmentTeardown

- ea: `0x140075214`
- end: `0x1400752b5`
- name: `VidXSchedulerVpEnlightenmentTeardown`
- size: `161`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14009958c`
- `0x14009999c`
- `0x1400f814c`

## callees

- `0x14000fa84`
- `0x140075214`
- `0x140099bd0`

## import_xrefs

- `winhvr!WinHvSetSchedulerAssistData` at `0x14007526f`
- `winhvr!WinHvSetSchedulerAssistData` at `0x14007526f`
- `winhvr!WinHvConfigureSchedulerAssistNotifications` at `0x140075253`
- `winhvr!WinHvConfigureSchedulerAssistNotifications` at `0x140075253`

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
0x140075214  mov     [rsp+arg_0], rbx
0x140075219  mov     [rsp+arg_8], rsi
0x14007521e  push    rdi
0x14007521f  sub     rsp, 20h
0x140075223  mov     rdi, [rcx+180h]
0x14007522a  mov     rbx, rcx
0x14007522d  test    rdi, rdi
0x140075230  jz      short loc_1400752A4
0x140075232  mov     rax, [rdi+28h]
0x140075236  test    rax, rax
0x140075239  jz      short loc_1400752A4
0x14007523b  cmp     dword ptr [rax], 1
0x14007523e  jnz     short loc_1400752A4
0x140075240  mov     rcx, [rcx]
0x140075243  xor     r9d, r9d
0x140075246  mov     edx, [rbx+8]
0x140075249  xor     r8d, r8d
0x14007524c  mov     rcx, [rcx+288h]
0x140075253  call    cs:__imp_WinHvConfigureSchedulerAssistNotifications
0x14007525a  nop     dword ptr [rax+rax+00h]
0x14007525f  mov     rcx, [rbx]
0x140075262  xor     r8d, r8d
0x140075265  mov     edx, [rbx+8]
0x140075268  mov     rcx, [rcx+288h]
0x14007526f  call    cs:__imp_WinHvSetSchedulerAssistData
0x140075276  nop     dword ptr [rax+rax+00h]
0x14007527b  mov     rsi, [rdi+28h]
0x14007527f  mov     qword ptr [rdi+28h], 0
0x140075287  cmp     qword ptr [rbx+150h], 0
0x14007528f  jz      short loc_140075299
0x140075291  mov     rcx, rbx
0x140075294  call    VidXSchedulerpSetThreadSchedulerAssist
0x140075299  mov     rcx, [rbx]
0x14007529c  mov     rdx, rsi
0x14007529f  call    VidXSchedulerpVpAssistContextTeardown
0x1400752a4  mov     rbx, [rsp+28h+arg_0]
0x1400752a9  mov     rsi, [rsp+28h+arg_8]
0x1400752ae  add     rsp, 20h
0x1400752b2  pop     rdi
0x1400752b3  retn
```
