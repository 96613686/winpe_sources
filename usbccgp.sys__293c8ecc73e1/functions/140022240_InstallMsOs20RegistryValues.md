# InstallMsOs20RegistryValues

- ea: `0x140022240`
- end: `0x140022315`
- name: `InstallMsOs20RegistryValues`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x1400242a4`

## callees

- `0x14000a6cc`
- `0x14000ed84`
- `0x140022240`
- `0x14002d748`
- `0x14002d9c4`

## pseudocode

```c
__int64 __fastcall InstallMsOs20RegistryValues(__int64 a1)
{
  unsigned __int16 *FunctionMsOs20FunctionSubset; // rax
  char *v3; // rbx
  const WCHAR *v4; // rdx
  int v5; // edx
  int v6; // edi
  const WCHAR *v8; // [rsp+48h] [rbp+10h] BYREF

  FunctionMsOs20FunctionSubset = (unsigned __int16 *)GetFunctionMsOs20FunctionSubset();
  if ( !FunctionMsOs20FunctionSubset )
    return 0;
  v3 = (char *)FunctionMsOs20FunctionSubset + FunctionMsOs20FunctionSubset[3];
  v4 = (unsigned __int16 *)((char *)FunctionMsOs20FunctionSubset + *FunctionMsOs20FunctionSubset);
  v8 = v4;
  while ( 1 )
  {
    if ( v4[1] == 4 )
    {
      v6 = SetPdoRegistryParameter(
             *(PDEVICE_OBJECT *)(a1 + 224),
             v4 + 4,
             (char *)v4 + v4[3] + 10,
             *(const WCHAR *)((char *)v4 + v4[3] + 8),
             v4[2]);
      if ( v6 < 0 )
        break;
    }
    if ( !(unsigned __int8)GetNextMsOs20Descriptor(v3, &v8) )
      return 3221225473LL;
    v4 = v8;
    if ( !v8 )
      return 0;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(a1 + 392), v5, 8, 72, (__int64)WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids, v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140022240  mov     [rsp+arg_0], rbx
0x140022245  mov     [rsp+arg_10], rsi
0x14002224a  push    rdi
0x14002224b  sub     rsp, 30h
0x14002224f  mov     rsi, rcx
0x140022252  call    GetFunctionMsOs20FunctionSubset
0x140022257  test    rax, rax
0x14002225a  jz      short loc_1400222BF
0x14002225c  movzx   ebx, word ptr [rax+6]
0x140022260  movzx   edx, word ptr [rax]
0x140022263  add     rbx, rax
0x140022266  add     rdx, rax
0x140022269  mov     [rsp+38h+arg_8], rdx
0x14002226e  cmp     word ptr [rdx+2], 4
0x140022273  jnz     short loc_1400222A4
0x140022275  movzx   eax, word ptr [rdx+6]
0x140022279  movzx   ecx, word ptr [rdx+4]
0x14002227d  mov     [rsp+38h+Type], ecx; Type
0x140022281  mov     rcx, [rsi+0E0h]; DeviceObject
0x140022288  movzx   r9d, word ptr [rax+rdx+8]
0x14002228e  lea     r8, [rax+0Ah]
0x140022292  add     r8, rdx
0x140022295  add     rdx, 8
0x140022299  call    SetPdoRegistryParameter
0x14002229e  mov     edi, eax
0x1400222a0  test    eax, eax
0x1400222a2  js      short loc_1400222D2
0x1400222a4  lea     rdx, [rsp+38h+arg_8]
0x1400222a9  mov     rcx, rbx
0x1400222ac  call    GetNextMsOs20Descriptor
0x1400222b1  test    al, al
0x1400222b3  jz      short loc_14002230E
0x1400222b5  mov     rdx, [rsp+38h+arg_8]
0x1400222ba  test    rdx, rdx
0x1400222bd  jnz     short loc_14002226E
0x1400222bf  xor     eax, eax
0x1400222c1  mov     rbx, [rsp+38h+arg_0]
0x1400222c6  mov     rsi, [rsp+38h+arg_10]
0x1400222cb  add     rsp, 30h
0x1400222cf  pop     rdi
0x1400222d0  retn
0x1400222d2  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400222d9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400222e0  jz      short loc_14002230A
0x1400222e2  mov     rcx, [rsi+188h]
0x1400222e9  lea     rax, WPP_5f3fca5046be3c4b9971a87d6c15ecbd_Traceguids
0x1400222f0  mov     r9d, 48h ; 'H'
0x1400222f6  mov     [rsp+38h+var_10], edi
0x1400222fa  mov     dl, 2
0x1400222fc  mov     qword ptr [rsp+38h+Type], rax
0x140022301  lea     r8d, [r9-40h]
0x140022305  call    WPP_RECORDER_SF_d
0x14002230a  mov     eax, edi
0x14002230c  jmp     short loc_1400222C1
0x14002230e  mov     eax, 0C0000001h
0x140022313  jmp     short loc_1400222C1
```
