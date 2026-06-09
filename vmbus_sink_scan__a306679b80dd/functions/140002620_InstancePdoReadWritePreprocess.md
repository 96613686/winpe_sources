# InstancePdoReadWritePreprocess

- ea: `0x140002620`
- end: `0x1400026aa`
- name: `InstancePdoReadWritePreprocess`
- size: `138`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140002000`
- `0x140002380`
- `0x140002620`
- `0x140017190`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140002690`
- `ntoskrnl!IofCompleteRequest` at `0x140002690`

## pseudocode

```c
__int64 __fastcall InstancePdoReadWritePreprocess(__int64 a1, __int64 a2)
{
  KSPIN_LOCK *v3; // rcx
  unsigned int v4; // ebx
  unsigned int v5; // eax

  v3 = *(KSPIN_LOCK **)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                          WdfDriverGlobals,
                          a1,
                          off_14001C160)
                      + 296);
  if ( !v3 )
  {
    v4 = -1073741808;
LABEL_7:
    *(_DWORD *)(a2 + 48) = v4;
    IofCompleteRequest((PIRP)a2, 0);
    return v4;
  }
  if ( **(_BYTE **)(a2 + 184) == 3 )
    v5 = PipeRead(v3, a2);
  else
    v5 = PipeWrite(v3);
  v4 = v5;
  if ( v5 != 259 )
    goto LABEL_7;
  return v4;
}

```

## disassembly

```asm
0x140002620  mov     [rsp+arg_0], rbx
0x140002625  push    rdi
0x140002626  sub     rsp, 20h
0x14000262a  mov     rax, cs:WdfFunctions_01033
0x140002631  mov     rdi, rdx
0x140002634  mov     r8, cs:off_14001C160
0x14000263b  mov     rdx, rcx
0x14000263e  mov     rcx, cs:WdfDriverGlobals
0x140002645  mov     rax, [rax+650h]
0x14000264c  call    _guard_dispatch_icall
0x140002651  mov     rcx, [rax+128h]; SpinLock
0x140002658  test    rcx, rcx
0x14000265b  jnz     short loc_140002664
0x14000265d  mov     ebx, 0C0000010h
0x140002662  jmp     short loc_140002688
0x140002664  mov     rax, [rdi+0B8h]
0x14000266b  mov     rdx, rdi
0x14000266e  cmp     byte ptr [rax], 3
0x140002671  jnz     short loc_14000267A
0x140002673  call    PipeRead
0x140002678  jmp     short loc_14000267F
0x14000267a  call    PipeWrite
0x14000267f  mov     ebx, eax
0x140002681  cmp     eax, 103h
0x140002686  jz      short loc_14000269C
0x140002688  xor     edx, edx; PriorityBoost
0x14000268a  mov     [rdi+30h], ebx
0x14000268d  mov     rcx, rdi; Irp
0x140002690  call    cs:__imp_IofCompleteRequest
0x140002697  nop     dword ptr [rax+rax+00h]
0x14000269c  mov     eax, ebx
0x14000269e  mov     rbx, [rsp+28h+arg_0]
0x1400026a3  add     rsp, 20h
0x1400026a7  pop     rdi
0x1400026a8  retn
```
