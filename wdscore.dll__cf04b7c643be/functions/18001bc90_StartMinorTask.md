# StartMinorTask

- ea: `0x18001bc90`
- end: `0x18001bd27`
- name: `StartMinorTask`
- size: `151`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001144`
- `0x180018020`
- `0x180019c80`
- `0x18001ab78`
- `0x18001bc90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001bca8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001bca8`

## pseudocode

```c
_QWORD *__fastcall StartMinorTask(char *a1)
{
  _QWORD *result; // rax
  _QWORD *v3; // rbx
  char *v4; // rdi
  _QWORD *v5; // rdi

  result = TlsGetValue(g_dwMajorTaskStackTLSIndex);
  if ( result )
  {
    result = (_QWORD *)CStack<CTaskNameCollection *>::Peek(result);
    v3 = result;
    if ( result )
    {
      v4 = "Def";
      if ( a1 )
        v4 = a1;
      result = operator new(0x10u);
      if ( result )
      {
        result = CTaskNameHolder::CTaskNameHolder((CTaskNameHolder *)result, v4);
        v5 = result;
        if ( result )
        {
          result = (_QWORD *)CDynamicArray<CTaskNameCollection *,CTaskNameCollection * *>::SetSize(
                               (__int64)(v3 + 2),
                               v3[3] + 1LL);
          *(_QWORD *)(v3[2] + 8LL * v3[3] - 8) = v5;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001bc90  mov     [rsp+arg_0], rbx
0x18001bc95  mov     [rsp+arg_8], rsi
0x18001bc9a  push    rdi
0x18001bc9b  sub     rsp, 20h
0x18001bc9f  mov     rsi, rcx
0x18001bca2  mov     ecx, cs:?g_dwMajorTaskStackTLSIndex@@3KA; dwTlsIndex
0x18001bca8  call    cs:__imp_TlsGetValue
0x18001bcaf  nop     dword ptr [rax+rax+00h]
0x18001bcb4  test    rax, rax
0x18001bcb7  jz      short loc_18001BD16
0x18001bcb9  mov     rcx, rax
0x18001bcbc  call    ?Peek@?$CStack@PEAVCTaskNameCollection@@@@QEAAPEAVCTaskNameCollection@@XZ; CStack<CTaskNameCollection *>::Peek(void)
0x18001bcc1  mov     rbx, rax
0x18001bcc4  test    rax, rax
0x18001bcc7  jz      short loc_18001BD16
0x18001bcc9  test    rsi, rsi
0x18001bccc  lea     rdi, aDef_0; "Def"
0x18001bcd3  mov     ecx, 10h; Size
0x18001bcd8  cmovnz  rdi, rsi
0x18001bcdc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bce1  test    rax, rax
0x18001bce4  jz      short loc_18001BD16
0x18001bce6  mov     rdx, rdi; char *
0x18001bce9  mov     rcx, rax; this
0x18001bcec  call    ??0CTaskNameHolder@@QEAA@PEBD@Z; CTaskNameHolder::CTaskNameHolder(char const *)
0x18001bcf1  mov     rdi, rax
0x18001bcf4  test    rax, rax
0x18001bcf7  jz      short loc_18001BD16
0x18001bcf9  mov     rdx, [rbx+18h]
0x18001bcfd  lea     rcx, [rbx+10h]
0x18001bd01  inc     rdx
0x18001bd04  call    ?SetSize@?$CDynamicArray@PEAVCTaskNameCollection@@PEAPEAV1@@@QEAAH_K@Z; CDynamicArray<CTaskNameCollection *,CTaskNameCollection * *>::SetSize(unsigned __int64)
0x18001bd09  mov     rdx, [rbx+18h]
0x18001bd0d  mov     rcx, [rbx+10h]
0x18001bd11  mov     [rcx+rdx*8-8], rdi
0x18001bd16  mov     rbx, [rsp+28h+arg_0]
0x18001bd1b  mov     rsi, [rsp+28h+arg_8]
0x18001bd20  add     rsp, 20h
0x18001bd24  pop     rdi
0x18001bd25  retn
```
