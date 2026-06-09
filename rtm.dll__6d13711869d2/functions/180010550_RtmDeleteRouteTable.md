# RtmDeleteRouteTable

- ea: `0x180010550`
- end: `0x1800106c1`
- name: `RtmDeleteRouteTable`
- size: `369`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007840`

## callees

- `0x180010550`
- `0x1800108f0`

## import_xrefs

- `ntdll!NtClose` at `0x18001062b`
- `ntdll!NtClose` at `0x180010636`
- `ntdll!NtClose` at `0x18001062b`
- `ntdll!NtClose` at `0x180010636`
- `ntdll!NtCancelTimer` at `0x18001060a`
- `ntdll!NtCancelTimer` at `0x180010617`
- `ntdll!NtCancelTimer` at `0x18001060a`
- `ntdll!NtCancelTimer` at `0x180010617`
- `KERNEL32!HeapFree` at `0x180010671`
- `KERNEL32!HeapFree` at `0x180010685`
- `KERNEL32!HeapFree` at `0x180010671`
- `KERNEL32!HeapFree` at `0x180010685`
- `KERNEL32!DeleteCriticalSection` at `0x1800106a7`
- `KERNEL32!DeleteCriticalSection` at `0x1800106a7`
- `KERNEL32!Sleep` at `0x1800105b7`
- `KERNEL32!Sleep` at `0x1800105c8`
- `KERNEL32!Sleep` at `0x1800105e8`
- `KERNEL32!Sleep` at `0x180010620`
- `KERNEL32!Sleep` at `0x18001063f`
- `KERNEL32!Sleep` at `0x1800105b7`
- `KERNEL32!Sleep` at `0x1800105c8`
- `KERNEL32!Sleep` at `0x1800105e8`
- `KERNEL32!Sleep` at `0x180010620`
- `KERNEL32!Sleep` at `0x18001063f`
- `KERNEL32!GlobalFree` at `0x18001065b`
- `KERNEL32!GlobalFree` at `0x18001065b`
- `KERNEL32!HeapDestroy` at `0x18001068f`
- `KERNEL32!HeapDestroy` at `0x18001068f`

## pseudocode

```c
__int64 __fastcall RtmDeleteRouteTable(int a1)
{
  __int32 v1; // edi
  __int64 v2; // rcx

  if ( a1 || !Tables )
    return 87;
  while ( (__int64 *)qword_18002BB10[28] != &qword_18002BB10[28] )
    RtmDeregisterClient((HGLOBAL)qword_18002BB10[28]);
  v1 = _InterlockedExchange(&dword_18002BB08, -10000) - 10000;
  while ( dword_18002BB08 > v1 )
    Sleep(0x64u);
  while ( _InterlockedIncrement((volatile signed __int32 *)&qword_18002BB10[4] + 1) > 0 )
  {
    while ( HIDWORD(qword_18002BB10[4]) != -1 )
      Sleep(0x64u);
  }
  while ( _InterlockedIncrement((volatile signed __int32 *)&qword_18002BB10[4]) > 0 )
  {
    while ( LODWORD(qword_18002BB10[4]) != -1 )
      Sleep(0x64u);
  }
  NtCancelTimer((HANDLE)qword_18002BB10[1], 0);
  NtCancelTimer((HANDLE)qword_18002BB10[0], 0);
  Sleep(0x64u);
  NtClose((HANDLE)qword_18002BB10[1]);
  NtClose((HANDLE)qword_18002BB10[0]);
  Sleep(0x64u);
  while ( 1 )
  {
    v2 = qword_18002BB10[5];
    if ( !qword_18002BB10[5] )
      break;
    qword_18002BB10[5] = *(_QWORD *)qword_18002BB10[5];
    GlobalFree((HGLOBAL)(v2 - 8));
  }
  HeapFree((HANDLE)Tables, 0, (LPVOID)qword_18002BB10[31]);
  HeapFree((HANDLE)Tables, 0, (LPVOID)qword_18002BB10[30]);
  HeapDestroy((HANDLE)Tables);
  Tables = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)&qword_18002BB10[41]);
  return 0;
}

```

## disassembly

```asm
0x180010550  push    rbx
0x180010552  push    rbp
0x180010553  push    rsi
0x180010554  push    rdi
0x180010555  push    r14
0x180010557  sub     rsp, 20h
0x18001055b  mov     ebp, 1
0x180010560  cmp     ecx, ebp
0x180010562  jnb     loc_1800106B1
0x180010568  mov     eax, ecx
0x18001056a  lea     rsi, Tables
0x180010571  lea     rbx, [rax+rax*2]
0x180010575  shl     rbx, 7
0x180010579  cmp     qword ptr [rbx+rsi], 0
0x18001057e  jz      loc_1800106B1
0x180010584  lea     rdi, [rsi+0F0h]
0x18001058b  add     rdi, rbx
0x18001058e  cmp     [rdi], rdi
0x180010591  jz      short loc_18001059D
0x180010593  mov     rcx, [rdi]; hMem
0x180010596  call    RtmDeregisterClient
0x18001059b  jmp     short loc_18001058E
0x18001059d  mov     edi, 0FFFFD8F0h
0x1800105a2  mov     r14d, 64h ; 'd'
0x1800105a8  xchg    edi, [rbx+rsi+8]
0x1800105ac  sub     edi, 2710h
0x1800105b2  jmp     short loc_1800105BD
0x1800105b4  mov     ecx, r14d; dwMilliseconds
0x1800105b7  call    cs:__imp_Sleep
0x1800105bd  cmp     [rbx+rsi+8], edi
0x1800105c1  jg      short loc_1800105B4
0x1800105c3  jmp     short loc_1800105D5
0x1800105c5  mov     ecx, r14d; dwMilliseconds
0x1800105c8  call    cs:__imp_Sleep
0x1800105ce  cmp     dword ptr [rbx+rsi+34h], 0FFFFFFFFh
0x1800105d3  jnz     short loc_1800105C5
0x1800105d5  mov     eax, ebp
0x1800105d7  lock xadd [rbx+rsi+34h], eax
0x1800105dd  add     eax, ebp
0x1800105df  test    eax, eax
0x1800105e1  jg      short loc_1800105CE
0x1800105e3  jmp     short loc_1800105F5
0x1800105e5  mov     ecx, r14d; dwMilliseconds
0x1800105e8  call    cs:__imp_Sleep
0x1800105ee  cmp     dword ptr [rbx+rsi+30h], 0FFFFFFFFh
0x1800105f3  jnz     short loc_1800105E5
0x1800105f5  mov     eax, ebp
0x1800105f7  lock xadd [rbx+rsi+30h], eax
0x1800105fd  add     eax, ebp
0x1800105ff  test    eax, eax
0x180010601  jg      short loc_1800105EE
0x180010603  mov     rcx, [rbx+rsi+18h]; TimerHandle
0x180010608  xor     edx, edx; CurrentState
0x18001060a  call    cs:__imp_NtCancelTimer
0x180010610  mov     rcx, [rbx+rsi+10h]; TimerHandle
0x180010615  xor     edx, edx; CurrentState
0x180010617  call    cs:__imp_NtCancelTimer
0x18001061d  mov     ecx, r14d; dwMilliseconds
0x180010620  call    cs:__imp_Sleep
0x180010626  mov     rcx, [rbx+rsi+18h]; Handle
0x18001062b  call    cs:__imp_NtClose
0x180010631  mov     rcx, [rbx+rsi+10h]; Handle
0x180010636  call    cs:__imp_NtClose
0x18001063c  mov     ecx, r14d; dwMilliseconds
0x18001063f  call    cs:__imp_Sleep
0x180010645  mov     rcx, [rbx+rsi+38h]
0x18001064a  test    rcx, rcx
0x18001064d  jz      short loc_180010663
0x18001064f  mov     rax, [rcx]
0x180010652  add     rcx, 0FFFFFFFFFFFFFFF8h; hMem
0x180010656  mov     [rbx+rsi+38h], rax
0x18001065b  call    cs:__imp_GlobalFree
0x180010661  jmp     short loc_180010645
0x180010663  mov     r8, [rbx+rsi+108h]; lpMem
0x18001066b  xor     edx, edx; dwFlags
0x18001066d  mov     rcx, [rbx+rsi]; hHeap
0x180010671  call    cs:__imp_HeapFree
0x180010677  mov     r8, [rbx+rsi+100h]; lpMem
0x18001067f  xor     edx, edx; dwFlags
0x180010681  mov     rcx, [rbx+rsi]; hHeap
0x180010685  call    cs:__imp_HeapFree
0x18001068b  mov     rcx, [rbx+rsi]; hHeap
0x18001068f  call    cs:__imp_HeapDestroy
0x180010695  lea     rcx, [rsi+158h]
0x18001069c  mov     qword ptr [rbx+rsi], 0
0x1800106a4  add     rcx, rbx; lpCriticalSection
0x1800106a7  call    cs:__imp_DeleteCriticalSection
0x1800106ad  xor     eax, eax
0x1800106af  jmp     short loc_1800106B6
0x1800106b1  mov     eax, 57h ; 'W'
0x1800106b6  add     rsp, 20h
0x1800106ba  pop     r14
0x1800106bc  pop     rdi
0x1800106bd  pop     rsi
0x1800106be  pop     rbp
0x1800106bf  pop     rbx
0x1800106c0  retn
```
