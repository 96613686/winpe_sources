# wistd::unique_ptr<ushort * [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<ushort * [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)

- ea: `0x14000888c`
- end: `0x1400088ad`
- name: `??1?$unique_ptr@$$BY0A@PEAGU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `HLOCAL __fastcall(HLOCAL *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000afda`

## callees

- `0x14000888c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400088a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400088a2`

## pseudocode

```c
HLOCAL __fastcall wistd::unique_ptr<unsigned short * [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned short * [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(
        HLOCAL *a1)
{
  HLOCAL result; // rax

  result = *a1;
  *a1 = 0;
  if ( result )
    return LocalFree(result);
  return result;
}

```

## disassembly

```asm
0x14000888c  sub     rsp, 28h
0x140008890  mov     rax, [rcx]
0x140008893  mov     qword ptr [rcx], 0
0x14000889a  test    rax, rax
0x14000889d  jz      short loc_1400088A8
0x14000889f  mov     rcx, rax; hMem
0x1400088a2  call    cs:__imp_LocalFree
0x1400088a8  add     rsp, 28h
0x1400088ac  retn
```
