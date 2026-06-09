# SkmiCopyDriverProxyEndpointInfoFromImage

- ea: `0x140081604`
- end: `0x140081764`
- name: `SkmiCopyDriverProxyEndpointInfoFromImage`
- size: `352`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400812f8`
- `0x1400820d4`

## callees

- `0x14000e460`
- `0x14000f0f0`
- `0x14001e2c4`
- `0x140037e68`
- `0x140060ad4`
- `0x140081604`
- `0x14008176c`
- `0x1400d7280`
- `0x1400f9780`

## pseudocode

```c
__int64 __fastcall SkmiCopyDriverProxyEndpointInfoFromImage(__int64 a1, __int64 a2, _QWORD *a3, _DWORD *a4)
{
  unsigned __int64 v4; // rdi
  __int64 v5; // rbp
  __int64 v6; // rsi
  void *Pool; // rax
  int v11; // ebx
  __int64 v12; // rbx
  unsigned __int64 v14; // [rsp+50h] [rbp+8h] BYREF
  __int64 v15; // [rsp+60h] [rbp+18h] BYREF

  *a3 = 0;
  v4 = 0;
  *a4 = 0;
  v5 = 0;
  v6 = *(_QWORD *)(a1 + 192);
  v14 = 0;
  if ( *(_QWORD *)(v6 + 32) )
  {
    Pool = (void *)SkAllocatePool(512, *(unsigned int *)(v6 + 60));
    *a3 = Pool;
    if ( Pool )
    {
      memmove(Pool, *(const void **)(v6 + 32), *(unsigned int *)(v6 + 60));
      v11 = 0;
      *a4 = *(_DWORD *)(v6 + 60);
      return (unsigned int)v11;
    }
    v11 = -1073741670;
    goto LABEL_14;
  }
  if ( _bittest16((const signed __int16 *)(a1 + 78), 8u) )
    return 0;
  if ( !a2 )
  {
    v11 = -1073741584;
    goto LABEL_14;
  }
  v12 = *(_QWORD *)(a1 + 48);
  if ( !v12 )
    return 0;
  v5 = SkiAttachProcess(PsIumSystemProcess);
  v11 = SkmiMapViewOfDriver(v12, a2, &v14);
  if ( v11 < 0 )
  {
    v4 = v14;
    goto LABEL_14;
  }
  v15 = 0;
  v4 = v14;
  RtlImageNtHeaderEx(1, v14, 0, &v15);
  v11 = SkmiCopyDriverProxyEndpointInfoFromNtHeader(v15, v4, a3, a4);
  if ( v11 < 0 )
  {
LABEL_14:
    if ( *a3 )
    {
      SkFreePool(512, *a3);
      *a3 = 0;
    }
  }
  if ( v4 )
    SkmiUnmapViewOfSection(v4, 0, 1);
  if ( v5 )
    SkiAttachProcess(v5);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140081604  mov     [rsp+arg_8], rbx
0x140081609  mov     [rsp+arg_18], rbp
0x14008160e  push    rsi
0x14008160f  push    rdi
0x140081610  push    r12
0x140081612  push    r14
0x140081614  push    r15
0x140081616  sub     rsp, 20h
0x14008161a  mov     qword ptr [r8], 0
0x140081621  xor     edi, edi
0x140081623  mov     dword ptr [r9], 0
0x14008162a  xor     ebp, ebp
0x14008162c  mov     rsi, [rcx+0C0h]
0x140081633  mov     r12, r9
0x140081636  mov     r14, r8
0x140081639  mov     [rsp+48h+arg_0], rdi
0x14008163e  mov     r15, rdx
0x140081641  cmp     [rsi+20h], rdi
0x140081645  jz      short loc_14008168A
0x140081647  mov     edx, [rsi+3Ch]
0x14008164a  mov     ecx, 200h
0x14008164f  mov     r8d, 78727044h
0x140081655  call    SkAllocatePool
0x14008165a  mov     [r14], rax
0x14008165d  test    rax, rax
0x140081660  jnz     short loc_14008166C
0x140081662  mov     ebx, 0C000009Ah
0x140081667  jmp     loc_140081711
0x14008166c  mov     r8d, [rsi+3Ch]; Size
0x140081670  mov     rcx, rax; void *
0x140081673  mov     rdx, [rsi+20h]; Src
0x140081677  call    memmove
0x14008167c  mov     eax, [rsi+3Ch]
0x14008167f  xor     ebx, ebx
0x140081681  mov     [r12], eax
0x140081685  jmp     loc_14008174A
0x14008168a  bt      word ptr [rcx+4Eh], 8
0x140081690  jnb     short loc_140081699
0x140081692  xor     ebx, ebx
0x140081694  jmp     loc_14008174A
0x140081699  test    r15, r15
0x14008169c  jnz     short loc_1400816A5
0x14008169e  mov     ebx, 0C00000F0h
0x1400816a3  jmp     short loc_140081711
0x1400816a5  mov     rbx, [rcx+30h]
0x1400816a9  test    rbx, rbx
0x1400816ac  jz      short loc_140081692
0x1400816ae  mov     rcx, cs:PsIumSystemProcess
0x1400816b5  call    SkiAttachProcess
0x1400816ba  lea     r8, [rsp+48h+arg_0]
0x1400816bf  mov     rdx, r15
0x1400816c2  mov     rcx, rbx
0x1400816c5  mov     rbp, rax
0x1400816c8  call    SkmiMapViewOfDriver
0x1400816cd  mov     ebx, eax
0x1400816cf  test    eax, eax
0x1400816d1  js      short loc_14008170C
0x1400816d3  xor     r8d, r8d
0x1400816d6  mov     [rsp+48h+arg_10], rdi
0x1400816db  mov     rdi, [rsp+48h+arg_0]
0x1400816e0  lea     r9, [rsp+48h+arg_10]
0x1400816e5  mov     rdx, rdi
0x1400816e8  lea     ecx, [r8+1]
0x1400816ec  call    RtlImageNtHeaderEx
0x1400816f1  mov     rcx, [rsp+48h+arg_10]
0x1400816f6  mov     r9, r12
0x1400816f9  mov     r8, r14
0x1400816fc  mov     rdx, rdi
0x1400816ff  call    SkmiCopyDriverProxyEndpointInfoFromNtHeader
0x140081704  mov     ebx, eax
0x140081706  test    eax, eax
0x140081708  jns     short loc_14008172A
0x14008170a  jmp     short loc_140081711
0x14008170c  mov     rdi, [rsp+48h+arg_0]
0x140081711  mov     rdx, [r14]
0x140081714  test    rdx, rdx
0x140081717  jz      short loc_14008172A
0x140081719  mov     ecx, 200h
0x14008171e  call    SkFreePool
0x140081723  mov     qword ptr [r14], 0
0x14008172a  test    rdi, rdi
0x14008172d  jz      short loc_14008173D
0x14008172f  xor     edx, edx
0x140081731  mov     rcx, rdi
0x140081734  lea     r8d, [rdx+1]
0x140081738  call    SkmiUnmapViewOfSection
0x14008173d  test    rbp, rbp
0x140081740  jz      short loc_14008174A
0x140081742  mov     rcx, rbp
0x140081745  call    SkiAttachProcess
0x14008174a  mov     rbp, [rsp+48h+arg_18]
0x14008174f  mov     eax, ebx
0x140081751  mov     rbx, [rsp+48h+arg_8]
0x140081756  add     rsp, 20h
0x14008175a  pop     r15
0x14008175c  pop     r14
0x14008175e  pop     r12
0x140081760  pop     rdi
0x140081761  pop     rsi
0x140081762  retn
```
