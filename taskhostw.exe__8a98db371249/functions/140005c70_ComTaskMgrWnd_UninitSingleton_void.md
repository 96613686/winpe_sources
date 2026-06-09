# ComTaskMgrWnd::UninitSingleton(void)

- ea: `0x140005c70`
- end: `0x140005cfc`
- name: `?UninitSingleton@ComTaskMgrWnd@@UEAAJXZ`
- size: `140`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140005c70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140005c8d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140005c8d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005ccc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140005ccc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005cde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005ced`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005cde`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005ced`

## pseudocode

```c
__int64 __fastcall ComTaskMgrWnd::UninitSingleton(HANDLE *this)
{
  HANDLE *v1; // rbx
  HANDLE *v3; // rdi
  HANDLE *v4; // rsi
  HANDLE v5; // rcx

  v1 = this + 7;
  v3 = this + 6;
  if ( SetEvent(this[7]) )
  {
    WaitForSingleObject(*v3, 0xFFFFFFFF);
    v4 = this + 7;
  }
  else
  {
    v4 = v1;
  }
  v5 = *v3;
  if ( *v3 )
  {
    if ( v5 != (HANDLE)-1LL )
    {
      CloseHandle(v5);
      *v3 = 0;
    }
  }
  else
  {
    v4 = v1;
  }
  if ( (char *)*v1 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(*v1);
    *v4 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x140005c70  mov     [rsp+arg_0], rbx
0x140005c75  mov     [rsp+arg_8], rsi
0x140005c7a  push    rdi
0x140005c7b  sub     rsp, 20h
0x140005c7f  lea     rbx, [rcx+38h]
0x140005c83  mov     rsi, rcx
0x140005c86  lea     rdi, [rcx+30h]
0x140005c8a  mov     rcx, [rbx]; hEvent
0x140005c8d  call    cs:__imp_SetEvent
0x140005c93  test    eax, eax
0x140005c95  jnz     short loc_140005CC4
0x140005c97  mov     rsi, rbx
0x140005c9a  mov     rcx, [rdi]; hObject
0x140005c9d  test    rcx, rcx
0x140005ca0  jnz     short loc_140005CD8
0x140005ca2  mov     rsi, rbx
0x140005ca5  mov     rcx, [rbx]; hObject
0x140005ca8  lea     rax, [rcx-1]
0x140005cac  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140005cb0  jbe     short loc_140005CED
0x140005cb2  mov     rbx, [rsp+28h+arg_0]
0x140005cb7  xor     eax, eax
0x140005cb9  mov     rsi, [rsp+28h+arg_8]
0x140005cbe  add     rsp, 20h
0x140005cc2  pop     rdi
0x140005cc3  retn
0x140005cc4  mov     rcx, [rdi]; hHandle
0x140005cc7  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x140005ccc  call    cs:__imp_WaitForSingleObject
0x140005cd2  add     rsi, 38h ; '8'
0x140005cd6  jmp     short loc_140005C9A
0x140005cd8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x140005cdc  jz      short loc_140005CA5
0x140005cde  call    cs:__imp_CloseHandle
0x140005ce4  mov     qword ptr [rdi], 0
0x140005ceb  jmp     short loc_140005CA5
0x140005ced  call    cs:__imp_CloseHandle
0x140005cf3  mov     qword ptr [rsi], 0
0x140005cfa  jmp     short loc_140005CB2
```
