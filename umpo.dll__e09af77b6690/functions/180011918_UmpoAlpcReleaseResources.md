# UmpoAlpcReleaseResources

- ea: `0x180011918`
- end: `0x18001196f`
- name: `UmpoAlpcReleaseResources`
- size: `87`
- prototype: `int __fastcall(HANDLE hObject)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800115f0`
- `0x180011790`

## callees

- `0x180011918`

## import_xrefs

- `ntdll!TpReleaseAlpcCompletion` at `0x18001192d`
- `ntdll!TpReleaseAlpcCompletion` at `0x18001192d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011946`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011958`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011946`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011958`

## pseudocode

```c
int __fastcall UmpoAlpcReleaseResources(HANDLE hObject)
{
  int result; // eax

  if ( UmpoAlpcCompletion )
  {
    result = TpReleaseAlpcCompletion();
    UmpoAlpcCompletion = 0;
  }
  if ( hObject )
    result = CloseHandle(hObject);
  if ( UmpoAlpcEvent )
  {
    result = CloseHandle(UmpoAlpcEvent);
    UmpoAlpcEvent = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180011918  push    rbx
0x18001191a  sub     rsp, 20h
0x18001191e  mov     rbx, rcx
0x180011921  mov     rcx, cs:UmpoAlpcCompletion
0x180011928  test    rcx, rcx
0x18001192b  jz      short loc_18001193E
0x18001192d  call    cs:__imp_TpReleaseAlpcCompletion
0x180011933  mov     cs:UmpoAlpcCompletion, 0
0x18001193e  test    rbx, rbx
0x180011941  jz      short loc_18001194C
0x180011943  mov     rcx, rbx; hObject
0x180011946  call    cs:__imp_CloseHandle
0x18001194c  mov     rcx, cs:UmpoAlpcEvent; hObject
0x180011953  test    rcx, rcx
0x180011956  jz      short loc_180011969
0x180011958  call    cs:__imp_CloseHandle
0x18001195e  mov     cs:UmpoAlpcEvent, 0
0x180011969  add     rsp, 20h
0x18001196d  pop     rbx
0x18001196e  retn
```
