# StartMajorTask

- ea: `0x18001bb80`
- end: `0x18001bc7e`
- name: `StartMajorTask`
- size: `254`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001144`
- `0x180018020`
- `0x180019c80`
- `0x180019e40`
- `0x18001bb80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001bb98`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001bb98`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001bbe8`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18001bbe8`

## pseudocode

```c
int __fastcall StartMajorTask(char *a1)
{
  CTaskNameHolder **Value; // rbx
  CTaskNameHolder **v3; // rax
  CTaskNameHolder *v4; // rax
  char *v5; // rsi
  CTaskNameHolder *v6; // rdi

  Value = (CTaskNameHolder **)TlsGetValue(g_dwMajorTaskStackTLSIndex);
  if ( Value
    || ((v3 = (CTaskNameHolder **)operator new(0x20u), (Value = v3) == 0)
      ? (Value = 0)
      : (CTaskNameHolder **)(v3[1] = 0, v3[2] = 0, *v3 = 0, v3[3] = (CTaskNameHolder *)10),
        LODWORD(v4) = TlsSetValue(g_dwMajorTaskStackTLSIndex, Value),
        (_DWORD)v4) )
  {
    v5 = "Def";
    if ( a1 )
      v5 = a1;
    v4 = (CTaskNameHolder *)operator new(0x30u);
    v6 = v4;
    if ( v4 )
    {
      CTaskNameHolder::CTaskNameHolder(v4, v5);
      *((_QWORD *)v6 + 3) = 0;
      *((_QWORD *)v6 + 4) = 0;
      *((_QWORD *)v6 + 2) = 0;
      *((_QWORD *)v6 + 5) = 10;
      CDynamicArray<CTaskNameCollection *,CTaskNameCollection * *>::SetSize(
        (__int64)Value,
        (unsigned __int64)Value[1] + 1);
      v4 = *Value;
      *((_QWORD *)*Value + (_QWORD)Value[1] - 1) = v6;
    }
  }
  else if ( Value )
  {
    LODWORD(v4) = CStack<CTaskNameCollection *>::`scalar deleting destructor'(Value);
  }
  return (int)v4;
}

```

## disassembly

```asm
0x18001bb80  mov     [rsp+arg_0], rbx
0x18001bb85  mov     [rsp+arg_8], rsi
0x18001bb8a  push    rdi
0x18001bb8b  sub     rsp, 20h
0x18001bb8f  mov     rdi, rcx
0x18001bb92  mov     ecx, cs:?g_dwMajorTaskStackTLSIndex@@3KA; dwTlsIndex
0x18001bb98  call    cs:__imp_TlsGetValue
0x18001bb9f  nop     dword ptr [rax+rax+00h]
0x18001bba4  mov     rbx, rax
0x18001bba7  test    rax, rax
0x18001bbaa  jnz     short loc_18001BC07
0x18001bbac  lea     ecx, [rax+20h]; Size
0x18001bbaf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bbb4  mov     rbx, rax
0x18001bbb7  test    rax, rax
0x18001bbba  jz      short loc_18001BBDD
0x18001bbbc  mov     qword ptr [rax+8], 0
0x18001bbc4  mov     qword ptr [rax+10h], 0
0x18001bbcc  mov     qword ptr [rax], 0
0x18001bbd3  mov     qword ptr [rax+18h], 0Ah
0x18001bbdb  jmp     short loc_18001BBDF
0x18001bbdd  xor     ebx, ebx
0x18001bbdf  mov     ecx, cs:?g_dwMajorTaskStackTLSIndex@@3KA; dwTlsIndex
0x18001bbe5  mov     rdx, rbx; lpTlsValue
0x18001bbe8  call    cs:__imp_TlsSetValue
0x18001bbef  nop     dword ptr [rax+rax+00h]
0x18001bbf4  test    eax, eax
0x18001bbf6  jnz     short loc_18001BC07
0x18001bbf8  test    rbx, rbx
0x18001bbfb  jz      short loc_18001BC6D
0x18001bbfd  mov     rcx, rbx; Block
0x18001bc00  call    ??_G?$CStack@PEAVCTaskNameCollection@@@@QEAAPEAXI@Z; CStack<CTaskNameCollection *>::`scalar deleting destructor'(uint)
0x18001bc05  jmp     short loc_18001BC6D
0x18001bc07  test    rdi, rdi
0x18001bc0a  lea     rsi, aDef_0; "Def"
0x18001bc11  mov     ecx, 30h ; '0'; Size
0x18001bc16  cmovnz  rsi, rdi
0x18001bc1a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bc1f  mov     rdi, rax
0x18001bc22  test    rax, rax
0x18001bc25  jz      short loc_18001BC6D
0x18001bc27  mov     rdx, rsi; char *
0x18001bc2a  mov     rcx, rax; this
0x18001bc2d  call    ??0CTaskNameHolder@@QEAA@PEBD@Z; CTaskNameHolder::CTaskNameHolder(char const *)
0x18001bc32  mov     qword ptr [rdi+18h], 0
0x18001bc3a  mov     rcx, rbx
0x18001bc3d  mov     qword ptr [rdi+20h], 0
0x18001bc45  mov     qword ptr [rdi+10h], 0
0x18001bc4d  mov     qword ptr [rdi+28h], 0Ah
0x18001bc55  mov     rdx, [rbx+8]
0x18001bc59  inc     rdx
0x18001bc5c  call    ?SetSize@?$CDynamicArray@PEAVCTaskNameCollection@@PEAPEAV1@@@QEAAH_K@Z; CDynamicArray<CTaskNameCollection *,CTaskNameCollection * *>::SetSize(unsigned __int64)
0x18001bc61  mov     rcx, [rbx+8]
0x18001bc65  mov     rax, [rbx]
0x18001bc68  mov     [rax+rcx*8-8], rdi
0x18001bc6d  mov     rbx, [rsp+28h+arg_0]
0x18001bc72  mov     rsi, [rsp+28h+arg_8]
0x18001bc77  add     rsp, 20h
0x18001bc7b  pop     rdi
0x18001bc7c  retn
```
