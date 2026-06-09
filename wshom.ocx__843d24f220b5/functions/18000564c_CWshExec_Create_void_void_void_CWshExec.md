# CWshExec::Create(void *,void *,void *,CWshExec * *)

- ea: `0x18000564c`
- end: `0x180005729`
- name: `?Create@CWshExec@@SAJPEAX00PEAPEAV1@@Z`
- size: `221`
- prototype: `__int64 __fastcall(HANDLE hObject, HANDLE, HANDLE, struct CWshExec **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d070`

## callees

- `0x18000564c`
- `0x1800060e4`
- `0x180006c74`
- `0x180011010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800056f8`
- `KERNEL32!CloseHandle` at `0x180005706`
- `KERNEL32!CloseHandle` at `0x180005714`
- `KERNEL32!CloseHandle` at `0x1800056f8`
- `KERNEL32!CloseHandle` at `0x180005706`
- `KERNEL32!CloseHandle` at `0x180005714`
- `ScrRun!DoOpenPipeStream` at `0x180005697`
- `ScrRun!DoOpenPipeStream` at `0x1800056af`
- `ScrRun!DoOpenPipeStream` at `0x1800056c5`
- `ScrRun!DoOpenPipeStream` at `0x180005697`
- `ScrRun!DoOpenPipeStream` at `0x1800056af`
- `ScrRun!DoOpenPipeStream` at `0x1800056c5`

## pseudocode

```c
__int64 __fastcall CWshExec::Create(HANDLE hObject, HANDLE a2, HANDLE a3, struct CWshExec **a4)
{
  CWshExec *v8; // rax
  CWshExec *v9; // rax
  struct CWshExec *v10; // rbx
  int v11; // edi

  *a4 = 0;
  v8 = (CWshExec *)operator new(0x88u);
  if ( v8 && (v9 = CWshExec::CWshExec(v8), (v10 = v9) != 0) )
  {
    v11 = DoOpenPipeStream(hObject, 1, (char *)v9 + 80);
    if ( v11 >= 0 )
    {
      hObject = 0;
      v11 = DoOpenPipeStream(a2, 2, (char *)v10 + 72);
      if ( v11 >= 0 )
      {
        v11 = DoOpenPipeStream(a3, 1, (char *)v10 + 88);
        if ( v11 >= 0 )
        {
          *a4 = v10;
          return 0;
        }
        a2 = 0;
      }
    }
    (*(void (__fastcall **)(struct CWshExec *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  else
  {
    v11 = -2147024882;
  }
  if ( hObject )
    CloseHandle(hObject);
  if ( a2 )
    CloseHandle(a2);
  if ( a3 )
    CloseHandle(a3);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000564c  push    rbx
0x18000564e  push    rbp
0x18000564f  push    rsi
0x180005650  push    rdi
0x180005651  push    r14
0x180005653  push    r15
0x180005655  sub     rsp, 28h
0x180005659  mov     rbp, rcx
0x18000565c  mov     qword ptr [r9], 0
0x180005663  mov     ecx, 88h; Size
0x180005668  mov     r15, r9
0x18000566b  mov     r14, r8
0x18000566e  mov     rsi, rdx
0x180005671  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005676  test    rax, rax
0x180005679  jz      short loc_1800056EB
0x18000567b  mov     rcx, rax; this
0x18000567e  call    ??0CWshExec@@AEAA@XZ; CWshExec::CWshExec(void)
0x180005683  mov     rbx, rax
0x180005686  test    rax, rax
0x180005689  jz      short loc_1800056EB
0x18000568b  lea     r8, [rax+50h]
0x18000568f  mov     edx, 1
0x180005694  mov     rcx, rbp
0x180005697  call    cs:__imp_DoOpenPipeStream
0x18000569d  mov     edi, eax
0x18000569f  test    eax, eax
0x1800056a1  js      short loc_1800056DA
0x1800056a3  xor     ebp, ebp
0x1800056a5  lea     r8, [rbx+48h]
0x1800056a9  mov     rcx, rsi
0x1800056ac  lea     edx, [rbp+2]
0x1800056af  call    cs:__imp_DoOpenPipeStream
0x1800056b5  mov     edi, eax
0x1800056b7  test    eax, eax
0x1800056b9  js      short loc_1800056DA
0x1800056bb  lea     r8, [rbx+58h]
0x1800056bf  mov     rcx, r14
0x1800056c2  lea     edx, [rbp+1]
0x1800056c5  call    cs:__imp_DoOpenPipeStream
0x1800056cb  mov     edi, eax
0x1800056cd  test    eax, eax
0x1800056cf  js      short loc_1800056D8
0x1800056d1  mov     [r15], rbx
0x1800056d4  xor     edi, edi
0x1800056d6  jmp     short loc_18000571A
0x1800056d8  xor     esi, esi
0x1800056da  mov     rax, [rbx]
0x1800056dd  mov     rcx, rbx
0x1800056e0  mov     rax, [rax+10h]
0x1800056e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056e9  jmp     short loc_1800056F0
0x1800056eb  mov     edi, 8007000Eh
0x1800056f0  test    rbp, rbp
0x1800056f3  jz      short loc_1800056FE
0x1800056f5  mov     rcx, rbp; hObject
0x1800056f8  call    cs:__imp_CloseHandle
0x1800056fe  test    rsi, rsi
0x180005701  jz      short loc_18000570C
0x180005703  mov     rcx, rsi; hObject
0x180005706  call    cs:__imp_CloseHandle
0x18000570c  test    r14, r14
0x18000570f  jz      short loc_18000571A
0x180005711  mov     rcx, r14; hObject
0x180005714  call    cs:__imp_CloseHandle
0x18000571a  mov     eax, edi
0x18000571c  add     rsp, 28h
0x180005720  pop     r15
0x180005722  pop     r14
0x180005724  pop     rdi
0x180005725  pop     rsi
0x180005726  pop     rbp
0x180005727  pop     rbx
0x180005728  retn
```
