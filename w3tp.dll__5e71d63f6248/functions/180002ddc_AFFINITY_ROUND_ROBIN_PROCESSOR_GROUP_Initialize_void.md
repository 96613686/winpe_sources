# AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::Initialize(void)

- ea: `0x180002ddc`
- end: `0x180002f84`
- name: `?Initialize@AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@QEAAJXZ`
- size: `424`
- prototype: `__int64 __fastcall(AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180002f8c`

## callees

- `0x180001e50`
- `0x180001f4c`
- `0x180001f8c`
- `0x180002a68`
- `0x180002ddc`
- `0x1800031d0`
- `0x1800041a6`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f0c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f1a`

## pseudocode

```c
__int64 __fastcall AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::Initialize(
        void **this,
        enum _LOGICAL_PROCESSOR_RELATIONSHIP a2)
{
  unsigned __int16 v2; // si
  int LogicalProcessorInfo; // eax
  _QWORD *v5; // rbp
  int v6; // edi
  unsigned __int64 v7; // rcx
  void *v8; // rax
  char *v9; // rax
  char *v10; // rcx
  __int64 v11; // rcx
  AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *v12; // rcx
  struct _PROC_THREAD_ATTRIBUTE_LIST **v13; // rcx
  HANDLE ProcessHeap; // rax
  unsigned __int16 i; // bp
  struct _PROC_THREAD_ATTRIBUTE_LIST **v16; // rcx
  LPVOID lpMem; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  lpMem = 0;
  LogicalProcessorInfo = AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::CreateLogicalProcessorInfo(
                           (AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *)this,
                           a2,
                           (struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX **)&lpMem);
  v5 = lpMem;
  v6 = LogicalProcessorInfo;
  if ( LogicalProcessorInfo >= 0 )
  {
    if ( *(_DWORD *)lpMem == 4 )
    {
      v7 = *((unsigned __int16 *)lpMem + 5);
      *((_WORD *)this + 4) = v7;
      v8 = operator new(saturated_mul(v7, 8u));
      this[2] = v8;
      if ( v8 )
      {
        memset_0(v8, 0, 8LL * *((unsigned __int16 *)this + 4));
        while ( v2 < *((_WORD *)this + 4) )
        {
          v9 = (char *)operator new(0x18u);
          v10 = v9;
          if ( v9 )
          {
            *(_QWORD *)v9 = 0;
            *(_OWORD *)(v9 + 8) = 0;
          }
          else
          {
            v10 = 0;
          }
          *((_QWORD *)this[2] + v2) = v10;
          v11 = *((_QWORD *)this[2] + v2);
          if ( !v11 )
            goto LABEL_16;
          *(_WORD *)(v11 + 16) = v2;
          v12 = (AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *)*((_QWORD *)this[2] + v2);
          *((_QWORD *)v12 + 1) = v5[6 * v2 + 9];
          v6 = AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::InitializeContext(
                 v12,
                 *((struct AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT **)this[2] + v2));
          if ( v6 < 0 )
          {
            v13 = (struct _PROC_THREAD_ATTRIBUTE_LIST **)*((_QWORD *)this[2] + v2);
            if ( v13 )
              AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT::`scalar deleting destructor'(v13);
            *((_QWORD *)this[2] + v2) = 0;
            break;
          }
          ++v2;
        }
      }
      else
      {
LABEL_16:
        v6 = -2147024888;
      }
    }
    else
    {
      v6 = -2147024883;
    }
  }
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
  if ( v6 < 0 && this[2] )
  {
    for ( i = 0; i < v2; ++i )
    {
      v16 = (struct _PROC_THREAD_ATTRIBUTE_LIST **)*((_QWORD *)this[2] + i);
      if ( v16 )
      {
        AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT::`scalar deleting destructor'(v16);
        *((_QWORD *)this[2] + i) = 0;
      }
    }
    operator delete(this[2]);
    this[2] = 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002ddc  mov     rax, rsp
0x180002ddf  mov     [rax+8], rbx
0x180002de3  mov     [rax+18h], rbp
0x180002de7  push    rsi
0x180002de8  push    rdi
0x180002de9  push    r14
0x180002deb  sub     rsp, 20h
0x180002def  xor     esi, esi
0x180002df1  lea     r8, [rax+10h]; struct _SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX **
0x180002df5  mov     [rax+10h], rsi
0x180002df9  mov     rbx, rcx
0x180002dfc  call    ?CreateLogicalProcessorInfo@AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@AEAAJW4_LOGICAL_PROCESSOR_RELATIONSHIP@@PEAPEAU_SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX@@@Z; AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::CreateLogicalProcessorInfo(_LOGICAL_PROCESSOR_RELATIONSHIP,_SYSTEM_LOGICAL_PROCESSOR_INFORMATION_EX * *)
0x180002e01  mov     rbp, [rsp+38h+lpMem]
0x180002e06  mov     edi, eax
0x180002e08  test    eax, eax
0x180002e0a  js      loc_180002F07
0x180002e10  cmp     dword ptr [rbp+0], 4
0x180002e14  jz      short loc_180002E20
0x180002e16  mov     edi, 8007000Dh
0x180002e1b  jmp     loc_180002F07
0x180002e20  movzx   eax, word ptr [rbp+0Ah]
0x180002e24  mov     ecx, eax
0x180002e26  mov     [rbx+8], ax
0x180002e2a  mov     eax, 8
0x180002e2f  mul     rcx
0x180002e32  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180002e39  cmovb   rax, rcx
0x180002e3d  mov     rcx, rax; Size
0x180002e40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002e45  mov     [rbx+10h], rax
0x180002e49  test    rax, rax
0x180002e4c  jz      loc_180002F02
0x180002e52  movzx   r8d, word ptr [rbx+8]
0x180002e57  xor     edx, edx; Val
0x180002e59  shl     r8, 3; Size
0x180002e5d  mov     rcx, rax; void *
0x180002e60  call    memset_0
0x180002e65  xor     eax, eax
0x180002e67  cmp     si, [rbx+8]
0x180002e6b  jnb     loc_180002F07
0x180002e71  mov     ecx, 18h; Size
0x180002e76  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002e7b  mov     rcx, rax
0x180002e7e  test    rax, rax
0x180002e81  jz      short loc_180002E93
0x180002e83  xorps   xmm0, xmm0
0x180002e86  mov     qword ptr [rax], 0
0x180002e8d  movups  xmmword ptr [rax+8], xmm0
0x180002e91  jmp     short loc_180002E95
0x180002e93  xor     ecx, ecx
0x180002e95  mov     rax, [rbx+10h]
0x180002e99  movzx   r14d, si
0x180002e9d  mov     [rax+r14*8], rcx
0x180002ea1  mov     rax, [rbx+10h]
0x180002ea5  mov     rcx, [rax+r14*8]
0x180002ea9  test    rcx, rcx
0x180002eac  jz      short loc_180002F02
0x180002eae  mov     [rcx+10h], si
0x180002eb2  lea     rdx, [r14+r14*2]
0x180002eb6  mov     rax, [rbx+10h]
0x180002eba  add     rdx, rdx
0x180002ebd  mov     rcx, [rax+r14*8]; this
0x180002ec1  mov     rax, [rbp+rdx*8+48h]
0x180002ec6  mov     [rcx+8], rax
0x180002eca  mov     rdx, [rbx+10h]
0x180002ece  mov     rdx, [rdx+r14*8]; struct AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT *
0x180002ed2  call    ?InitializeContext@AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@AEAAJPEAUTHREAD_AFFINITY_CONTEXT@1@@Z; AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::InitializeContext(AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT *)
0x180002ed7  mov     edi, eax
0x180002ed9  test    eax, eax
0x180002edb  js      short loc_180002EE2
0x180002edd  inc     si
0x180002ee0  jmp     short loc_180002E67
0x180002ee2  mov     rax, [rbx+10h]
0x180002ee6  mov     rcx, [rax+r14*8]; this
0x180002eea  test    rcx, rcx
0x180002eed  jz      short loc_180002EF4
0x180002eef  call    ??_GTHREAD_AFFINITY_CONTEXT@AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@QEAAPEAXI@Z; AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT::`scalar deleting destructor'(uint)
0x180002ef4  mov     rax, [rbx+10h]
0x180002ef8  mov     qword ptr [rax+r14*8], 0
0x180002f00  jmp     short loc_180002F07
0x180002f02  mov     edi, 80070008h
0x180002f07  test    rbp, rbp
0x180002f0a  jz      short loc_180002F20
0x180002f0c  call    cs:__imp_GetProcessHeap
0x180002f12  mov     r8, rbp; lpMem
0x180002f15  xor     edx, edx; dwFlags
0x180002f17  mov     rcx, rax; hHeap
0x180002f1a  call    cs:__imp_HeapFree
0x180002f20  test    edi, edi
0x180002f22  jns     short loc_180002F6F
0x180002f24  cmp     qword ptr [rbx+10h], 0
0x180002f29  jz      short loc_180002F6F
0x180002f2b  xor     ebp, ebp
0x180002f2d  xor     eax, eax
0x180002f2f  cmp     ax, si
0x180002f32  jnb     short loc_180002F5E
0x180002f34  mov     rax, [rbx+10h]
0x180002f38  movzx   r14d, bp
0x180002f3c  mov     rcx, [rax+r14*8]; this
0x180002f40  test    rcx, rcx
0x180002f43  jz      short loc_180002F56
0x180002f45  call    ??_GTHREAD_AFFINITY_CONTEXT@AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@QEAAPEAXI@Z; AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT::`scalar deleting destructor'(uint)
0x180002f4a  mov     rax, [rbx+10h]
0x180002f4e  mov     qword ptr [rax+r14*8], 0
0x180002f56  inc     bp
0x180002f59  cmp     bp, si
0x180002f5c  jb      short loc_180002F34
0x180002f5e  mov     rcx, [rbx+10h]; Block
0x180002f62  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002f67  mov     qword ptr [rbx+10h], 0
0x180002f6f  mov     rbx, [rsp+38h+arg_0]
0x180002f74  mov     eax, edi
0x180002f76  mov     rbp, [rsp+38h+arg_10]
0x180002f7b  add     rsp, 20h
0x180002f7f  pop     r14
0x180002f81  pop     rdi
0x180002f82  pop     rsi
0x180002f83  retn
```
