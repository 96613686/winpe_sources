# RDCameraDeviceManager::RemoveAllRDCameraDevicesAsync(void)

- ea: `0x180008380`
- end: `0x180008456`
- name: `?RemoveAllRDCameraDevicesAsync@RDCameraDeviceManager@@AEAAJXZ`
- size: `214`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180033374`

## callees

- `0x180008380`
- `0x18000b8f8`
- `0x18000b98c`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008414`
- `KERNEL32!SubmitThreadpoolWork` at `0x18000843a`
- `KERNEL32!SubmitThreadpoolWork` at `0x18000843a`
- `KERNEL32!CloseThreadpoolWork` at `0x180008443`
- `KERNEL32!CloseThreadpoolWork` at `0x180008443`
- `KERNEL32!CreateThreadpoolWork` at `0x18000839e`
- `KERNEL32!CreateThreadpoolWork` at `0x18000839e`

## pseudocode

```c
signed int __fastcall RDCameraDeviceManager::RemoveAllRDCameraDevicesAsync(char *pv)
{
  struct _TP_WORK *ThreadpoolWork; // rdi
  signed int LastError; // eax
  char v4; // bl
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int result; // eax

  ThreadpoolWork = CreateThreadpoolWork(
                     RDCameraDeviceManager::RemoveAllRDCameraDevicesWorkCallback,
                     pv,
                     (PTP_CALLBACK_ENVIRON)(pv + 640));
  if ( ThreadpoolWork )
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)pv + 8LL))(pv);
    SubmitThreadpoolWork(ThreadpoolWork);
    CloseThreadpoolWork(ThreadpoolWork);
    return 0;
  }
  else
  {
    if ( *(unsigned int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 28LL) & 8) != 0
      && *(_BYTE *)(*(_QWORD *)&WPP_GLOBAL_Control + 25LL) >= 2u )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = LastError;
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 16LL),
        49,
        (unsigned int)WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"pWork",
        v4);
    }
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180008380  mov     [rsp+arg_0], rbx
0x180008385  push    rdi
0x180008386  sub     rsp, 30h
0x18000838a  mov     rbx, rcx
0x18000838d  lea     r8, [rcx+280h]; pcbe
0x180008394  mov     rdx, rcx; pv
0x180008397  lea     rcx, ?RemoveAllRDCameraDevicesWorkCallback@RDCameraDeviceManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000839e  call    cs:__imp_CreateThreadpoolWork
0x1800083a4  mov     rdi, rax
0x1800083a7  test    rax, rax
0x1800083aa  jnz     short loc_180008428
0x1800083ac  mov     rax, cs:WPP_GLOBAL_Control
0x1800083b3  lea     rcx, WPP_GLOBAL_Control
0x1800083ba  cmp     rax, rcx
0x1800083bd  jz      short loc_180008414
0x1800083bf  test    byte ptr [rax+1Ch], 8
0x1800083c3  jz      short loc_180008414
0x1800083c5  cmp     byte ptr [rax+19h], 2
0x1800083c9  jb      short loc_180008414
0x1800083cb  call    cs:__imp_GetLastError
0x1800083d1  mov     ebx, eax
0x1800083d3  test    eax, eax
0x1800083d5  jle     short loc_1800083E0
0x1800083d7  movzx   ebx, ax
0x1800083da  or      ebx, 80070000h
0x1800083e0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800083e5  lea     rcx, aPwork; "pWork"
0x1800083ec  mov     [rsp+38h+var_10], ebx
0x1800083f0  mov     [rsp+38h+var_18], rcx
0x1800083f5  lea     r8, WPP_c432f270cc673c149d2fdc2d74a41b79_Traceguids
0x1800083fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180008403  mov     edx, 31h ; '1'
0x180008408  mov     r9d, eax
0x18000840b  mov     rcx, [rcx+10h]
0x18000840f  call    WPP_SF_DsD
0x180008414  call    cs:__imp_GetLastError
0x18000841a  test    eax, eax
0x18000841c  jle     short loc_18000844B
0x18000841e  movzx   eax, ax
0x180008421  or      eax, 80070000h
0x180008426  jmp     short loc_18000844B
0x180008428  mov     rcx, [rbx]
0x18000842b  mov     rax, [rcx+8]
0x18000842f  mov     rcx, rbx
0x180008432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008437  mov     rcx, rdi; pwk
0x18000843a  call    cs:__imp_SubmitThreadpoolWork
0x180008440  mov     rcx, rdi; pwk
0x180008443  call    cs:__imp_CloseThreadpoolWork
0x180008449  xor     eax, eax
0x18000844b  mov     rbx, [rsp+38h+arg_0]
0x180008450  add     rsp, 30h
0x180008454  pop     rdi
0x180008455  retn
```
