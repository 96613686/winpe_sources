# DataStoreClient::Shutdown(void)

- ea: `0x180054c80`
- end: `0x180054cd9`
- name: `?Shutdown@DataStoreClient@@UEAAXXZ`
- size: `89`
- prototype: `void __fastcall(DataStoreClient *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18003d140`
- `0x180043eec`

## callees

- `0x180054c80`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180054cb7`
- `KERNEL32!EnterCriticalSection` at `0x180054cb7`
- `KERNEL32!LeaveCriticalSection` at `0x180054cd2`
- `KERNEL32!SwitchToThread` at `0x180054cac`
- `KERNEL32!SwitchToThread` at `0x180054cac`
- `KERNEL32!TryEnterCriticalSection` at `0x180054c9b`
- `KERNEL32!TryEnterCriticalSection` at `0x180054c9b`

## pseudocode

```c
void __fastcall DataStoreClient::Shutdown(DataStoreClient *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  int v3; // ebx

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  v3 = 0;
  while ( !TryEnterCriticalSection(v2) )
  {
    if ( ++v3 >= 100 )
    {
      EnterCriticalSection(v2);
      break;
    }
    SwitchToThread();
  }
  --*((_DWORD *)this + 12);
  LeaveCriticalSection(v2);
}

```

## disassembly

```asm
0x180054c80  mov     [rsp+arg_0], rbx
0x180054c85  mov     [rsp+arg_8], rsi
0x180054c8a  push    rdi
0x180054c8b  sub     rsp, 20h
0x180054c8f  mov     rsi, rcx
0x180054c92  lea     rdi, [rcx+8]
0x180054c96  xor     ebx, ebx
0x180054c98  mov     rcx, rdi; lpCriticalSection
0x180054c9b  call    cs:__imp_TryEnterCriticalSection
0x180054ca1  test    eax, eax
0x180054ca3  jnz     short loc_180054CBD
0x180054ca5  inc     ebx
0x180054ca7  cmp     ebx, 64h ; 'd'
0x180054caa  jge     short loc_180054CB4
0x180054cac  call    cs:__imp_SwitchToThread
0x180054cb2  jmp     short loc_180054C98
0x180054cb4  mov     rcx, rdi; lpCriticalSection
0x180054cb7  call    cs:__imp_EnterCriticalSection
0x180054cbd  dec     dword ptr [rsi+30h]
0x180054cc0  mov     rcx, rdi
0x180054cc3  mov     rbx, [rsp+28h+arg_0]
0x180054cc8  mov     rsi, [rsp+28h+arg_8]
0x180054ccd  add     rsp, 20h
0x180054cd1  pop     rdi
0x180054cd2  jmp     cs:__imp_LeaveCriticalSection
```
