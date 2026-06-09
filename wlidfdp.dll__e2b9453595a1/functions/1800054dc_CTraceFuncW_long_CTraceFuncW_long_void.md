# CTraceFuncW<long>::~CTraceFuncW<long>(void)

- ea: `0x1800054dc`
- end: `0x18000557d`
- name: `??1?$CTraceFuncW@J@@QEAA@XZ`
- size: `161`
- prototype: `int __fastcall(__int64, __int64, int)`
- caller_count: `17`
- callee_count: `4`
- tags: ``

## callers

- `0x180005d3c`
- `0x180007120`
- `0x180007b00`
- `0x18000a134`
- `0x18000a3e8`
- `0x18000ab84`
- `0x18000aec0`
- `0x18000b080`
- `0x18000b700`
- `0x18000bc8c`
- `0x18000dc00`
- `0x180010818`
- `0x180010b07`
- `0x180010e6f`
- `0x180010eb7`
- `0x1800110d9`
- `0x180011142`

## callees

- `0x1800054dc`
- `0x180008f6c`
- `0x180008fd4`
- `0x1800099a8`

## pseudocode

```c
int __fastcall CTraceFuncW<long>::~CTraceFuncW<long>(__int64 a1, __int64 a2, int a3)
{
  unsigned int *v3; // rax
  unsigned __int64 v4; // rdx
  unsigned int v5; // r9d
  MsaTracingInternal *v6; // r8
  __int64 v7; // rcx
  __int64 *v8; // rdx

  v3 = *(unsigned int **)(a1 + 8);
  v4 = 0;
  v5 = *v3;
  if ( (*v3 & 0x80000000) == 0 )
  {
    LODWORD(v3) = MsaTracingInternal::TraceFunctionExit(*(MsaTracingInternal **)a1, (const char *)v5, a3);
    return (int)v3;
  }
  if ( *(_QWORD *)(a1 + 16) )
  {
    while ( v4 < *(_QWORD *)(a1 + 16) )
    {
      v3 = *(unsigned int **)(a1 + 24);
      if ( v5 == v3[v4] )
      {
        LODWORD(v3) = MsaTracingInternal::TraceFunctionWarning(*(MsaTracingInternal **)a1, (const char *)v5, a3);
        return (int)v3;
      }
      ++v4;
    }
  }
  v6 = *(MsaTracingInternal **)a1;
  v7 = (unsigned int)(dword_180020A0C - 1);
  if ( dword_180020A0C == 1 )
  {
    if ( (byte_180020581 & 8) == 0 )
      return (int)v3;
    v8 = LiveSsp_TraceFunction_Failure;
    goto LABEL_17;
  }
  v7 = (unsigned int)(dword_180020A0C - 2);
  if ( dword_180020A0C == 2 )
  {
    if ( (byte_180020582 & 8) == 0 )
      return (int)v3;
    v8 = CredProv_TraceFunction_Failure;
LABEL_17:
    LODWORD(v3) = McTemplateU0sd_EventWriteTransfer(v7, v8, v6);
    return (int)v3;
  }
  if ( dword_180020A0C == 3 && (byte_180020583 & 8) != 0 )
  {
    v8 = WlidNsp_TraceFunction_Failure;
    goto LABEL_17;
  }
  return (int)v3;
}

```

## disassembly

```asm
0x1800054dc  sub     rsp, 28h
0x1800054e0  mov     rax, [rcx+8]
0x1800054e4  xor     edx, edx
0x1800054e6  mov     r9d, [rax]
0x1800054e9  test    r9d, r9d
0x1800054ec  js      short loc_1800054FD
0x1800054ee  mov     rcx, [rcx]; this
0x1800054f1  mov     edx, r9d; char *
0x1800054f4  add     rsp, 28h
0x1800054f8  jmp     ?TraceFunctionExit@MsaTracingInternal@@YAKPEBDJ@Z; MsaTracingInternal::TraceFunctionExit(char const *,long)
0x1800054fd  cmp     [rcx+10h], rdx
0x180005501  jbe     short loc_180005527
0x180005503  cmp     rdx, [rcx+10h]
0x180005507  jnb     short loc_180005527
0x180005509  mov     rax, [rcx+18h]
0x18000550d  cmp     r9d, [rax+rdx*4]
0x180005511  jz      short loc_180005518
0x180005513  inc     rdx
0x180005516  jmp     short loc_180005503
0x180005518  mov     rcx, [rcx]; this
0x18000551b  mov     edx, r9d; char *
0x18000551e  add     rsp, 28h
0x180005522  jmp     ?TraceFunctionWarning@MsaTracingInternal@@YAKPEBDJ@Z; MsaTracingInternal::TraceFunctionWarning(char const *,long)
0x180005527  mov     r8, [rcx]
0x18000552a  mov     ecx, cs:dword_180020A0C
0x180005530  sub     ecx, 1
0x180005533  jz      short loc_180005563
0x180005535  sub     ecx, 1
0x180005538  jz      short loc_180005551
0x18000553a  cmp     ecx, 1
0x18000553d  jnz     short loc_180005578
0x18000553f  test    cs:byte_180020583, 8
0x180005546  jz      short loc_180005578
0x180005548  lea     rdx, WlidNsp_TraceFunction_Failure
0x18000554f  jmp     short loc_180005573
0x180005551  test    cs:byte_180020582, 8
0x180005558  jz      short loc_180005578
0x18000555a  lea     rdx, CredProv_TraceFunction_Failure
0x180005561  jmp     short loc_180005573
0x180005563  test    cs:byte_180020581, 8
0x18000556a  jz      short loc_180005578
0x18000556c  lea     rdx, LiveSsp_TraceFunction_Failure
0x180005573  call    McTemplateU0sd_EventWriteTransfer
0x180005578  add     rsp, 28h
0x18000557c  retn
```
