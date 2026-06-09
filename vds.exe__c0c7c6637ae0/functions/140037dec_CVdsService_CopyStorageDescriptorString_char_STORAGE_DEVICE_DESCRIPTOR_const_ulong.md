# CVdsService::CopyStorageDescriptorString(char * *,_STORAGE_DEVICE_DESCRIPTOR const *,ulong)

- ea: `0x140037dec`
- end: `0x140037ef8`
- name: `?CopyStorageDescriptorString@CVdsService@@CAJPEAPEADPEBU_STORAGE_DEVICE_DESCRIPTOR@@K@Z`
- size: `268`
- prototype: `__int64 __fastcall(char **, const struct _STORAGE_DEVICE_DESCRIPTOR *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140025e20`

## callees

- `0x14002de26`
- `0x140037dec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140037e71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140037e71`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140037e15`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x140037e15`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140037e98`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140037ebe`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140037edd`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140037e98`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140037ebe`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x140037edd`
- `vdsutil!VdsTraceW` at `0x140037e43`
- `vdsutil!VdsTraceW` at `0x140037e88`
- `vdsutil!VdsTraceW` at `0x140037ed1`
- `vdsutil!VdsTraceW` at `0x140037e43`
- `vdsutil!VdsTraceW` at `0x140037e88`
- `vdsutil!VdsTraceW` at `0x140037ed1`

## string_xrefs

- `0x140037e04`: `CVdsService::CopyStorageDescriptorString`
- `0x140037ec8`: `CVdsService::CopyStorageDescriptorString, 1`
- `0x140037e3a`: `CVdsService::CopyStorageDescriptorString, 2`
- `0x140037e7f`: `CVdsService::CopyStorageDescriptorString, 3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVdsService::CopyStorageDescriptorString(
        char **a1,
        const struct _STORAGE_DEVICE_DESCRIPTOR *a2,
        unsigned int a3)
{
  __int64 v3; // rdi
  char *v6; // rdi
  unsigned int v7; // ebx
  __int64 v8; // rbx
  char *v9; // rax
  _BYTE v11[24]; // [rsp+20h] [rbp-18h] BYREF

  v3 = a3;
  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v11, 0x5Eu, "CVdsService::CopyStorageDescriptorString");
  if ( a1 && a2 )
  {
    *a1 = 0;
    v6 = (char *)a2 + v3;
    if ( v6 )
    {
      v8 = -1;
      do
        ++v8;
      while ( v6[v8] );
      while ( (_DWORD)v8 )
      {
        if ( v6[(unsigned int)(v8 - 1)] != 32 )
        {
          v9 = (char *)CoTaskMemAlloc((unsigned int)(v8 + 1));
          *a1 = v9;
          if ( !v9 )
          {
            VdsTraceW(0, L"CVdsService::CopyStorageDescriptorString, 3");
            v7 = -2147024882;
            goto LABEL_12;
          }
          memcpy_0(v9, v6, (unsigned int)v8);
          (*a1)[(unsigned int)v8] = 0;
          break;
        }
        LODWORD(v8) = v8 - 1;
      }
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v11);
      return 0;
    }
    else
    {
      VdsTraceW(0, L"CVdsService::CopyStorageDescriptorString, 2");
      v7 = -2147024883;
LABEL_12:
      CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v11);
      return v7;
    }
  }
  else
  {
    VdsTraceW(0, L"CVdsService::CopyStorageDescriptorString, 1");
    CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v11);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140037dec  mov     [rsp+arg_0], rbx
0x140037df1  mov     [rsp+arg_8], rsi
0x140037df6  push    rdi
0x140037df7  sub     rsp, 30h
0x140037dfb  mov     edi, r8d
0x140037dfe  mov     rbx, rdx
0x140037e01  mov     rsi, rcx
0x140037e04  lea     r8, aCvdsserviceCop_5; "CVdsService::CopyStorageDescriptorStrin"...
0x140037e0b  mov     edx, 5Eh ; '^'
0x140037e10  lea     rcx, [rsp+38h+var_18]
0x140037e15  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x140037e1b  nop
0x140037e1c  test    rsi, rsi
0x140037e1f  jz      loc_140037EC8
0x140037e25  test    rbx, rbx
0x140037e28  jz      loc_140037EC8
0x140037e2e  mov     qword ptr [rsi], 0
0x140037e35  add     rdi, rbx
0x140037e38  jnz     short loc_140037E50
0x140037e3a  lea     rdx, aCvdsserviceCop_0; "CVdsService::CopyStorageDescriptorStrin"...
0x140037e41  xor     ecx, ecx
0x140037e43  call    cs:__imp_VdsTraceW
0x140037e49  mov     ebx, 8007000Dh
0x140037e4e  jmp     short loc_140037E93
0x140037e50  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140037e54  inc     rbx
0x140037e57  cmp     byte ptr [rdi+rbx], 0
0x140037e5b  jnz     short loc_140037E54
0x140037e5d  test    ebx, ebx
0x140037e5f  jz      short loc_140037EB9
0x140037e61  lea     ecx, [rbx-1]
0x140037e64  cmp     byte ptr [rcx+rdi], 20h ; ' '
0x140037e68  jnz     short loc_140037E6E
0x140037e6a  mov     ebx, ecx
0x140037e6c  jmp     short loc_140037E5D
0x140037e6e  lea     ecx, [rbx+1]; cb
0x140037e71  call    cs:__imp_CoTaskMemAlloc
0x140037e77  mov     [rsi], rax
0x140037e7a  test    rax, rax
0x140037e7d  jnz     short loc_140037EA2
0x140037e7f  lea     rdx, aCvdsserviceCop_2; "CVdsService::CopyStorageDescriptorStrin"...
0x140037e86  xor     ecx, ecx
0x140037e88  call    cs:__imp_VdsTraceW
0x140037e8e  mov     ebx, 8007000Eh
0x140037e93  lea     rcx, [rsp+38h+var_18]
0x140037e98  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140037e9e  mov     eax, ebx
0x140037ea0  jmp     short loc_140037EE8
0x140037ea2  mov     ebx, ebx
0x140037ea4  mov     r8d, ebx; Size
0x140037ea7  mov     rdx, rdi; Src
0x140037eaa  mov     rcx, rax; void *
0x140037ead  call    memcpy_0
0x140037eb2  mov     rax, [rsi]
0x140037eb5  mov     byte ptr [rbx+rax], 0
0x140037eb9  lea     rcx, [rsp+38h+var_18]
0x140037ebe  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140037ec4  xor     eax, eax
0x140037ec6  jmp     short loc_140037EE8
0x140037ec8  lea     rdx, aCvdsserviceCop_4; "CVdsService::CopyStorageDescriptorStrin"...
0x140037ecf  xor     ecx, ecx
0x140037ed1  call    cs:__imp_VdsTraceW
0x140037ed7  nop
0x140037ed8  lea     rcx, [rsp+38h+var_18]
0x140037edd  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x140037ee3  mov     eax, 80070057h
0x140037ee8  mov     rbx, [rsp+38h+arg_0]
0x140037eed  mov     rsi, [rsp+38h+arg_8]
0x140037ef2  add     rsp, 30h
0x140037ef6  pop     rdi
0x140037ef7  retn
```
