# THREAD_POOL_DATA::ThreadPoolThread(void *)

- ea: `0x180001010`
- end: `0x180001084`
- name: `?ThreadPoolThread@THREAD_POOL_DATA@@SAKPEAX@Z`
- size: `116`
- prototype: `__int64 __fastcall(THREAD_POOL_DATA *this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001010`
- `0x180001090`
- `0x180003c84`

## pseudocode

```c
__int64 __fastcall THREAD_POOL_DATA::ThreadPoolThread(THREAD_POOL_DATA *this)
{
  unsigned int v2; // ecx
  BOOL v3; // esi
  unsigned int i; // edi

  v2 = *((_DWORD *)this + 12);
  v3 = v2 >= _InterlockedIncrement((volatile signed __int32 *)this + 4);
  for ( i = THREAD_POOL_DATA::ThreadPoolThread(this); !*((_DWORD *)this + 7); i = THREAD_POOL_DATA::ThreadPoolThread(this) )
  {
    if ( !v3 && !(unsigned int)ThreadHasIOPending() )
      break;
  }
  _InterlockedDecrement((volatile signed __int32 *)this + 4);
  return i;
}

```

## disassembly

```asm
0x180001010  mov     [rsp+arg_0], rbx
0x180001015  mov     [rsp+arg_8], rsi
0x18000101a  push    rdi
0x18000101b  sub     rsp, 20h
0x18000101f  mov     edx, 1
0x180001024  mov     rbx, rcx
0x180001027  mov     ecx, [rcx+30h]
0x18000102a  mov     eax, edx
0x18000102c  lock xadd [rbx+10h], eax
0x180001031  inc     eax
0x180001033  xor     esi, esi
0x180001035  cmp     ecx, eax
0x180001037  mov     rcx, rbx; this
0x18000103a  cmovnb  esi, edx
0x18000103d  call    ?ThreadPoolThread@THREAD_POOL_DATA@@QEAAKXZ; THREAD_POOL_DATA::ThreadPoolThread(void)
0x180001042  cmp     dword ptr [rbx+1Ch], 0
0x180001046  mov     edi, eax
0x180001048  jnz     short loc_18000106E
0x18000104a  nop     word ptr [rax+rax+00h]
0x180001050  cmp     esi, 1
0x180001053  jz      short loc_18000105E
0x180001055  call    ?ThreadHasIOPending@@YAHXZ; ThreadHasIOPending(void)
0x18000105a  test    eax, eax
0x18000105c  jz      short loc_18000106E
0x18000105e  mov     rcx, rbx; this
0x180001061  call    ?ThreadPoolThread@THREAD_POOL_DATA@@QEAAKXZ; THREAD_POOL_DATA::ThreadPoolThread(void)
0x180001066  cmp     dword ptr [rbx+1Ch], 0
0x18000106a  mov     edi, eax
0x18000106c  jz      short loc_180001050
0x18000106e  lock dec dword ptr [rbx+10h]
0x180001072  mov     eax, edi
0x180001074  mov     rbx, [rsp+28h+arg_0]
0x180001079  mov     rsi, [rsp+28h+arg_8]
0x18000107e  add     rsp, 20h
0x180001082  pop     rdi
0x180001083  retn
```
